# Course Overview

## From Prototype to Production

Plenty of courses teach you to beat a benchmark in a notebook, and plenty more teach you to pitch a demo, hackathon style. But a demo has no real customer, no real deployment, and no real stakes: nobody depends on it, nothing breaks when it fails, and nobody needs to maintain it. This CMU course is about the hard part that comes next: turning that prototype into a **production-grade AI-powered software system** that delivers value to actual customers, that you deploy in the real world, and that keeps running, keeps getting updated, and adapts to changing conditions without going up in flames through security holes, safety incidents, or silent quality collapse.

You will learn AI engineering end to end, working across **traditional machine learning, large language models, and, increasingly, AI agents that take actions in the real world**: how to build the system around the model, ship it, know whether it actually works, anticipate the ways it will fail, and keep it operating and improving under real load. Along the way, we examine how familiar software engineering practices must adapt when system behavior is probabilistic, depends on data, and evolves over time. Because models make mistakes, and agents act on those mistakes, **managing risk runs through the entire course**, alongside MLOps and responsible AI (safety, security, explainability, fairness). The emphasis is on engineering complete systems that people can depend on.

This course is adapted from [Machine Learning in Production](https://mlip-cmu.github.io/f2026/) (17-445/17-645/17-745) for an audience that is already familiar with software engineering practices. This Spring 2027 offering is designed for students with a software engineering background (e.g., 17-313 or equivalent experience with testing, requirements, architecture, process, and teamwork), some data science and GenAI experience (e.g., has taken a machine learning course, has used sklearn and LLMs), and basic programming skills (e.g., Python programming with libraries, navigating a Unix shell). Rather than introducing software engineering fundamentals, the course builds on them and focuses on what changes when systems depend on learned models, data, and agents.

## Official Course Description

This course prepares software engineers to build and operate production-grade systems powered by machine learning. Assuming prior knowledge of software engineering and basic machine learning, it examines how established engineering practices must adapt to probabilistic, data-dependent, and continuously evolving behavior. Students study the full application lifecycle for systems integrating ML models, large language models, and AI agents. Topics include MLOps practices such as pipeline automation, versioning, reproducibility, deployment, monitoring, and drift detection; harness engineering for increasingly autonomous systems, including orchestration, evaluation, guardrails, permissions, and human oversight; and system-level qualities such as safety, security, privacy, fairness, and explainability.

## Who This Course Is For

This course is for students who want to **build and operate AI-powered software systems** that people can depend on. We assume familiarity with core software engineering practices from **17-313 or equivalent experience or coursework**, along with basic machine learning, including training and evaluating a model. Building on that foundation, we explore what it takes to deploy a model, determine whether it works well enough, manage its failures, and operate and improve the system as data and the world change.

The course is particularly suited to **software engineers who want to build production ML systems and AI agents**, including students interested in roles such as **AI Engineer, ML Engineer, MLOps Engineer,** or **Forward Deployed Engineer**. Students will learn how to adapt familiar engineering practices to systems whose behavior depends on learned models, data, and probabilistic outputs. Through hands-on work, they will gain experience with ML pipelines, deployment, monitoring, behavioral testing, and production infrastructure.

The course also introduces **harness engineering** for AI agents: the tools, context, execution controls, and evaluation mechanisms that support reliable operation. Students will apply these ideas to an operations agent that uses production monitoring tools to help investigate incidents, with attention to permissions, security, failure recovery, and human oversight.

## What We Cover

Building on prior experience or coursework in software engineering and machine learning, we focus on the engineering challenges of building, deploying, and operating production ML systems, with additional emphasis on AI agents and harness engineering.

We cover topics such as:

- **How do we design for wrong predictions a model may make?** How do we anticipate mistakes, assess risks, and assure *safety* despite possible errors? How do we design the *user interface* and the entire system to mitigate the consequences of mistakes? Where should we introduce *human oversight*?
- **How do we build and operate reliable AI agents?** How does *harness engineering* support agents through context management, tool interfaces, and execution control? How do we connect agents to tools and APIs through protocols such as *MCP*? How do we use *tracing*, permissions, approval boundaries, and failure recovery to support reliable operation? How do we evaluate and secure an operations agent that helps diagnose production incidents?
- **How do we reliably deploy, monitor, and update models in production?** How do *MLOps* tools support pipeline automation and continuous delivery? How do we manage *versioning*, *provenance*, and *reproducibility* across code, data, and models? How do we monitor system behavior, detect *data quality* issues and *concept drift*, and support safe updates and rollback?
- **How do we scale production ML systems?** How do we handle growing volumes of training data, telemetry, and prediction requests? How do we use *stream processing* and production infrastructure to support reliable data ingestion and model serving? How do we balance *latency*, *throughput*, resource use, and operating cost?
- **How do we test and evaluate production ML systems and agents?** How do we assess *model quality* beyond aggregate accuracy through data slicing and *behavioral testing*? How do we test data transformations, model integration, and entire ML pipelines? How do we incorporate these checks into *continuous integration*? For agents, how do we evaluate tool use, execution trajectories, and responses to tool failures and injected incidents?
- **Which qualities matter beyond prediction accuracy?** How do we identify and measure application-specific requirements for *latency*, *cost*, *scalability*, *explainability*, *fairness*, and *safety*? How do we make model predictions and agent actions understandable? How do we recognize *feedback loops*, address accountability, and resolve conflicts among quality requirements?

**Production-ready tools.** You will gain familiarity with production-quality infrastructure tools. These are likely to include stream processing with Apache Kafka, test automation with GitHub Actions, monitoring and experiment tracking with tools such as Prometheus, Grafana, DVC, and Weights & Biases, and deployment with Docker, Kubernetes, and various MLOps tools. The exact set is still being finalized. Familiarity with these tools has helped many past Machine Learning in Production students in technical interviews.

**Examples and case studies.** We explore real products with commercial potential, going beyond benchmark tasks. For example, instead of object detection in the abstract, we look at how to use it in delivery robots or for image search on a photo-sharing site. Some of these products may be less flashy but have real commercial potential today, such as customer support agents, insurance fraud investigation, content recommendation, meeting minutes generated from recordings, and disease diagnosis.

**An extended team project.** Your team will build, deploy, evaluate, and maintain a robust and scalable movie recommendation service under realistic production conditions, serving one million active users. This is not a toy: your system runs live for several weeks and is graded on how it holds up under real load and changing conditions, as well as on the quality of your engineering decisions and evaluation. You will feel firsthand what breaks when a model meets production, and how to fix it.

## Practical Learning Experience

Through individual assignments, practical labs, case studies, and an extended team project, students will gain experience with:

- Building and evaluating the complete software system around a model.
- Using production infrastructure for automated testing, deployment, monitoring, and experiment tracking.
- Making pipelines and experiments reproducible.
- Identifying failures and responding to changing data and operating conditions.
- Designing safeguards, permissions, and human oversight for increasingly autonomous systems.
- Reasoning about tradeoffs among quality, latency, operating cost, scalability, safety, security, privacy, fairness, and explainability.

Examples and case studies emphasize real applications with practical and commercial value, going beyond isolated benchmark tasks.

!!! note
    Specific tools and detailed course content are still being planned.

## Course Details

- **Course number:** 17-444
- **Course title:** Production Machine Learning Systems for Software Engineers
- **Units:** 9
- **Schedule:** Two sessions per week, usually lectures; recitations every other week.
- **Expected background:** Prior knowledge of software engineering and basic machine learning.
- **Software engineering preparation:** 17-313, or significant software engineering experience subject to instructor approval.
- **Counts toward:** CS elective.
- **Additional credit:** Software Engineering Concentration credit to be confirmed.
- **Final exam:** None.

## Proposed Assessment Structure

!!! warning "Proposed"
    The assessment structure below is proposed and may change before the semester begins.

| Component | Weight | Description |
|---|---:|---|
| Individual assignments | 35% | Implementation, evaluation, and written analysis applying course concepts. |
| Team project | 30% | Building, deploying, evaluating, and maintaining an AI-powered service through staged milestones. |
| Midterms | 20% | Applying course concepts and reasoning through engineering decisions and tradeoffs. |
| Labs | 10% | Practical exercises with production AI engineering tools and workflows. |
| Participation | 5% | Contributions to discussions and in-class activities. |
| **Total** | **100%** | **No final exam.** |
