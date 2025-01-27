---
title: My thoughs on how to build software fast
date: 2025-01-27
tags:
    - software_development
categories:
    - builder
keywords:
    - sofware_develoment
---
# The Ideal Software Builder

Imagine making a change and receiving instant feedback. Programming is iterative, and instant feedback is crucial. Early issue detection is cheaper and more efficient.

# What Does a Feedback System Look Like?

Effective feedback in software comes from practices like TDD, Pair/Mob programming, automation testing, CI/CD, and E2E testing. These aim to provide early feedback. Yet, many struggle with these practices.

# Why We Struggle with Productivity Practices

## Our story

I lead a team using Strapi to manage short videos. Initially, we focused on understanding our tools rather than fighting them. We didn't adopt TDD due to inexperience and perceived difficulty. With tight deadlines, we faced several challenges:

* Context switching sensitivity
* Lack of mastery in mock frameworks
* Framework-dependent code
* Rush to deliver
* Impatience

Most of our code interacts with the database, making real database tests necessary. However, setting up and running these tests is time-consuming, especially with Strapi, which takes seconds to start.

Strapi is not a test-friendly framework, thus hindering productivity.

> Instead of writing bad tests, we chose to skip testing altogether.


# Measuring Developer Productivity

Measuring developer productivity can be misleading, as developers may game the system. Instead, focus on practices and factors that indicate team productivity:

* Speed of feature delivery
* Feedback turnaround time
* Frequency of refactoring
* Team-wide participation in refactoring
* Test execution speed

Evaluate these metrics and encourage the team to improve them for increased productivity and satisfaction.
# The Way Forward

The key takeaway is to build an instant feedback loop. How?

### Tooling
* Choose test-friendly tools
* Use tools that easily create test data
* Opt for fast-running tools
* Automate the above steps

### Mindset
* Continuously learn tools and frameworks
* Spread knowledge among team members
* Practice knowledge sharing (Pair/Mob programming)
* Adopt an automation mindset



