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

![Diagram](diagram.jpg)

[!(Video)](https://drive.google.com/file/d/1rQ9mCtRjmY40LvZW1R_IWhIw-sIEvBvi/view?usp=sharing)

## Comments
https://docs.google.com/forms/d/1HOGyN7R0X7IxZQgd1W-rE6EnoC1Kqt41RtmEVqb6fMY/edit
