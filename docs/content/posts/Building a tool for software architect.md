---
title: Building a Tool for Software Architects
date: 2025-01-27
tags:
    - software_development
categories:
    - builder
keywords:
    - software_development
---

# Pain Points

As a software architect and tech lead who codes daily, I frequently face these challenges:

* Communicating architecture to team members
* Keeping architecture and decisions up to date
* Identifying and educating the team on patterns
* Maintaining codebase health

Once the product is in operation, additional challenges include:
* Identifying and troubleshooting infrastructure issues
* Debugging application issues via logs and tracing
* Collaborating with POs, engineers, and QA

# Desired Tools

Imagine tools that boost my performance 1000x.

### Design Phase
A tool to describe architecture in C4 language, visualize it, and keep it updated by editing the C4 file stored in the same git repository as the code.

### Operating Phase
A tool that connects architecture components to deployed infrastructure, providing a holistic view of health, logs, and metrics.

  * Quickly access logs and health checks in a single tool.

Additionally, a tool that maps architecture to the code repository and uses LLM to:

  * Maintain codebase health
    * Identify missing patterns
    * Detect code structure issues
    * Suggest refactoring
    * Support local code reviews before PR submission

# Future Workflow

This tool will be my go-to upon signing in. It will show:

* Architecture
* System health
* Codebase health
* TO-DOs

Example scenarios:

Person A: "I can't make an API call, can you check?"
Me: 
    $ show me service XXX
    Health: yes
    Errors in last 5 minutes: Yes. Click to view details

Quickly, I can answer and view logs. Woohoo!

Person B: "Who consumes this event?"
Me: 
    $ show architecture
    [Visualizing]

I can quickly show who consumes and produces events, and guide them to do it themselves as the tool stores data in the code repository.

That's it! The 1000x performance tool for software architects.
