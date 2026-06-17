---
# Fill in the fields below to create a basic custom agent for your repository.
# The Copilot CLI can be used for local testing: https://gh.io/customagents/cli
# To make this agent available, merge this file into the default repository branch.
# For format details, see: https://gh.io/customagents/config

name: my-agent
description: Runs the main workflow and fixes errors when possible.
---

# My Agent

Run workflow `main.yml`; if errors occur, fix them before completing.

This agent runs your primary workflow and iterates on fixes when failures are detected.
