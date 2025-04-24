# LLM Agents for System Engineering in Factorio

A capstone project exploring how large language models (LLMs) can be guided to perform complex automation tasks within the game Factorio, using structured prompts, abstraction mods, and RCON-controlled execution.

---

## Introduction

Autonomous AI agents have the potential to transform how we manage large-scale systems. However, traditional benchmarks fail to capture the planning, adaptability, and trade-offs found in real-world system engineering.

This project uses Factorio as a dynamic testbed to evaluate LLMs through a custom prompt-based interface and a modded DSL, enabling agents to design, build, and scale functioning factories in-game.

![Poster](poster.jpg)
---

## Architecture

- Prompts are stored locally and sent via a Java class
- Java communicates with the LLM (OpenAI API)
- Returned commands are parsed and dispatched to a local Factorio server via RCON
- Factory updates are monitored and scored manually or automatically

```mermaid
flowchart TD
    A[Local Factorio Server] <--> B[RCON Protocol]
    
    C[Java Class] --> D[Read Prompts File]
    D --> E[Send Prompt to LLM]
    E --> F[LLM Processes Prompt]
    F --> G[LLM Generates Response]
    G --> H[Java Class Receives Response]
    
    H -->|Contains Command?| I{Command Check}
    I -->|Yes| J[Extract Command]
    J --> K[Send Command to RCON]
    K --> B
    
    I -->|No| L[Process Non-Command Response]
    L --> E
