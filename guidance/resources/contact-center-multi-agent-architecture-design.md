---
title: Single-agent and multi-agent architectures
description: Find tips for how to design autonomous service agents in Dynamics 365 and compare multi-agent architecture versus a single-agent design. Learn when to use either approach and how to move from one to the other.
author: edupont04
contributors:
 - ktaylor
 - lishelk
 - asinyagin
ms.topic: concept-article
ms.date: 09/08/2025
ms.author: edupont
ms.reviewer: edupont
---

# Single-agent and multi-agent architectures for AI agents in contact centers

When you design intelligent systems, consider where your system fits on the spectrum between single-agent and multi-agent systems. Software systems often start as single-agent systems and can evolve into multi-agent systems. This evolution affects scalability, maintainability, adaptability, performance, and user experience. This article gives practical guidance for developers, showing how to approach system design and growth, including the strengths and limitations of each architecture. For multi-agent architectures, this article looks at two key coordination paradigms: *domain-based agentic workflows* and *LLM-driven agent orchestrator workflows*. It highlights their trade-offs and ideal use cases, and uses real-world examples to illustrate these decisions. The article uses the term *agent* for agentic capabilities that you build with Microsoft Copilot Studio or similar. The term doesn't apply to human customer service representatives.

## What is single-agent architecture?

A single-agent architecture is an intelligent system with one entity that perceives its environment, makes decisions, reasons, and acts to achieve its goals. The agent uses logic, knowledge, and actions to meet its objectives.

Use single-agent architecture when you want to work around issues such as the following list:

- *Single-task domains*  

  Use when the problem scope is well defined, narrow, and manageable by one entity.
- *Centralized control*  

  Choose when centralized reasoning and decision making are better, like in environments where coordination and communication between entities add unnecessary complexity.
- *Single context*  

  Use when all context for the task is in one place and can be structured as a single knowledge repository.
- *Limited resources*  

  Pick when system resources (computation, memory, energy) are limited and can't efficiently support multiple agents.
- *Predictable environments*  

  Use if the operating environment is static or predictable, so a single agent can perform optimally.
- *Maintainability*  

  Choose for applications that need to be simple to test, debug, or deploy. Single-agent systems are easier to maintain.

### Advantages to single-agent architecture

The following table outlines the main advantages you get by choosing a single-agent architecture.

|Issue |Advantage of single-agent architecture|
|---------|---------|
|Simplicity|It's easier to design, implement, test, and maintain.|
|Lower overhead|There's no need for inter-agent communication, so computational and networking overhead is lower.|
|More predictable behavior|There are fewer sources of randomness and unexpected interactions.|
|Transparent debugging|It's easier to trace and diagnose issues with a single entity managing all logic.|

But there are also challenges. The following table outlines the potential disadvantages.

|Issue |Drawbacks of single-agent architecture|
|---------|---------|
|Lack of scalability|As complexity grows, single-agent performance suffers. Large context windows and retrieval-augmented generation (RAG) pipelines spread attention across more tokens, increasing compute cost and response quality variance. Long prompts often suffer from the "lost in the middle" effect, where relevant information buried deep in context is ignored. Adding more retrieved information chunks can dilute precision, amplify noise, and increase position bias. Having many tools can lead to tool-selection errors and latency. These effects make single-agent designs more brittle at scale.|
|Limited modularity| It's harder to separate concerns and extend functionality incrementally.|
|Reduced robustness| A failure in the agent can impact the entire system.|
|Poor suitability for distributed problems| Single-agent systems aren't ideal for tasks naturally distributed across multiple dynamic entities.|

### Examples of single-agent architectures

- Personal productivity bots: Calendar assistants that schedule meetings for one user.
- Customer care agents: An agent that handles customer care for a business. More complex customer care systems can use multi-agent architecture.

Other examples include chess-playing AI that operates as a single agent searching for optimal moves. Similarly, robotic vacuum cleaners are autonomous units that clean an environment without interacting with other agents.

## What is multi-agent architecture?

Multi-agent architectures have multiple autonomous agents that interact in a shared or distributed environment. These agents can cooperate, compete, or work independently, and each has unique capabilities, knowledge, or perspectives. Agents pursue local objectives and contribute to system-level goals through coordination or negotiation. Agents communicate through explicit messaging or shared context. Coordination can be centralized, decentralized, or hybrid. Agent autonomy is limited by roles, permissions, and assigned domains or tasks.

Use multi-agent architecture when you want to work around issues such as the following list:

- *Decomposable problems*  

  A multi-agent architecture can help you split tasks and delegate them to specialized agents.
- *Dynamic and complex environments*  

  A multi-agent architecture can help you when a single perspective isn't enough, or when the environment changes quickly.
- *Scalability needs*  

  A multi-agent architecture can help you parallelize the workload or add agents to handle growth or redundancy.
- *Distributed control*  

  A multi-agent architecture can help you when a single centralized controller isn't optimal or possible.
- *Dynamic or unpredictable paths to solution*  

  A multi-agent architecture can help you when there's no single fixed path to the outcome.
- *Fault tolerance*  

  Multi-agent systems can recover from the failure of individual agents without collapsing.

There are challenges in multi-agent architectures, though. For example, it can be complex to share context between agents, and to coordinate and delegate between agents. Also, small changes to orchestration can lead to significant changes in behavior and outcomes.

### Advantages to multi-agent architecture

The following table outlines the main advantages you get by choosing a multi-agent architecture.

|Issue |Advantage of multi-agent architecture|
|---------|---------|
|Parallelism|Multiple agents work on different subtasks at the same time for better performance.|
|Specialization|Agents are tailored for specific roles, which improves efficiency and adaptability.|
|Redundancy|The system can handle individual agent failures, so it's more robust.|
|Emergent behavior|Complex behaviors can come from agent interactions, which can solve problems that are hard for single agents.|
|Modularity|It's easier to add, remove, or upgrade individual agents.|

As mentioned, there are also challenges. The following table outlines the potential disadvantages.

|Issue |Drawbacks of multi-agent architecture|
|---------|---------|
|Increased complexity|Needs sophisticated coordination, communication, and conflict resolution.|
|Higher resource consumption| Multiple agents can use more computing and communication resources.|
|Nondeterministic outcomes| Emergent behaviors and interactions can make system behavior harder to predict and test.|
|Risk of compounding errors| Errors in reasoning, planning, and goal evaluation can add up and cause system failure. You might need corrective mechanisms.|
|Debugging difficulty|It's harder to trace bugs and understand failures because responsibilities are distributed.|
|Optimization difficulty| Because of the complexity, optimizing the system takes more effort.|

### Guidelines for multi-agent systems

- Specify what agents do and how they check if they achieve their objective.

- Clearly specify work division and subtask descriptions by orchestrator. This helps avoid duplicate work or missed subtasks.

- Specify task and subtask complexity, and allocate agents appropriately.

- Parallelize tasks and tool use among agents to decrease time to result.

- Use subagent output to artifact store to avoid imprecise communication through orchestrator or other agents.

### Examples of multi-agent architectures

- Software development system where agents represent several roles, like developer, architect, project manager, code reviewer, security specialist, and tester. These systems often outperform single-agent systems.

- Research system where agents pursue different research directions at once.

- Project management system where agents identify issues, assign issues to human programmers, run build and CI/CD pipelines, check results, summarize progress, and report to the project manager.

- Multi-agent conversational AI in systems where different bots, such as booking, information, and troubleshooting agents, work together to resolve complex user requests.

- Smart grid systems where agents representing power producers, consumers, and grid operators coordinate for optimal energy flow.

- Automated financial trading where multiple bots with different trading strategies interact in real-time markets.

- Collaborative robotics (swarm robotics) such as drones or robots work together for tasks like search and rescue, mapping, or delivery.

## Compare deterministic agentic workflows to LLM-orchestrator-based agentic workflows

A deterministic agentic workflow uses explicit, predefined rules or protocols to govern agent interactions, coordination, and task delegation. The sequence of operations, agent responsibilities, and communication flows are set in advance.

- *Predictability*: The system behaves consistently under identical circumstances, which is useful for critical applications where reliability matters most.

- *Simpler debugging*: Failures and unexpected behaviors are easier to trace.

  Use in customer care scenarios and software development systems.

- *Limitations*: Less adaptable to new scenarios, and often harder to extend as complexity grows.

In contrast, an LLM orchestrator-based agentic workflow uses a large language model to dynamically coordinate, instruct, and mediate between agents. The LLM interprets goals, creates strategies, assigns tasks, and helps agents communicate using natural language or structured prompts.

- *Adaptability*: The LLM adapts workflows on the fly, handling new agents, unexpected user intents, or changing environments.

- *Natural language coordination*: Agents communicate and receive instructions in human-like language, making integration and flexibility easier.

- *Emergent solutions*: The LLM creates creative and contextually appropriate strategies that rigid protocols can't predict.

  Use for research systems where the number and direction of subtasks aren't known beforehand. Also use for computer control scenarios where agents need to perform different control, input, and website information processing steps to achieve user goals.

- *Limitations*: Potential for unpredictable or unexpected behaviors, harder to guarantee reliability, and greater resource requirements for running LLMs in production.

The following table compares the two approaches:

|Deterministic agentic workflows  |LLM orchestrator-based workflows |
|---------|---------|
|Best for well defined, safety critical, or regulatory environments.|Best for open ended, creative, or complex domains where adaptability is critical.|
|Use when system behavior must be explainable.|Use when user interaction is dynamic or when integrating many specialized agents.|
|Best for real-time systems where latency and predictability matter more than flexibility.|Best for applications where workflow logic can change often or unpredictably. |

## Agent-based architecture for Dynamics 365 Contact Center

The same architecture principles apply to Customer Intent Agent. Customer Intent Agent for Voice uses generative AI to identify customer intents in the Dynamics 365 Contact Center environment. This agent acts as a frontline service representative. It improves self-service experiences by helping customer service representatives quickly understand the customer's needs, guide discussions with relevant follow-up questions, and deliver personalized solutions instantly. Learn more at [Overview of Customer Intent Agent](/dynamics365/contact-center/administer/overview-customer-intent-agent).

Customer Intent Agent for Voice is a single agent that orchestrates the entire conversation. One agent handles the full process: planning the conversation flow, getting knowledge from databases or documentation, and using tools as needed. This centralized agent keeps context and manages user interactions, ensuring a consistent and unified approach to each problem.

While the agent can delegate specific tasks by using tools, orchestration and conversation control stay with a single agent. This design removes communication and coordination overhead, resulting in one or a few LLM calls per turn, which reduces latency and resource use. Scale test results for Customer Intent Agent for Voice show a P95 turn latency of 1.6 seconds.

The architecture also supports the conversation growing into multi-agent conversations through delegation and consultancy. This approach gives you the benefits of a multi-agent system while keeping the advantages of a single orchestration agent. This agent also works in a multi-agent ecosystem in the contact center, and it's overseen by other agents, such as the Quality Evaluation Agent. Learn more about automating intent discovery and resolution with Customer Intent Agent in our blog post at [Automate intent discovery and resolution with Customer Intent Agent](https://www.microsoft.com/dynamics-365/blog/it-professional/2025/08/19/automate-intent-discovery-and-resolution-with-customer-intent-agent/)

## Best practices

Choose between single and multi-agent architectures based on the problem domain, scalability needs, and operational constraints. Single agent architectures offer simplicity and predictability, so they're ideal for contained, well understood domains. Multi-agent architectures work well in complex, distributed, and dynamic environments, but need careful design to manage complexity.

For multi-agent systems, choosing between deterministic workflows and AI-based orchestrator approaches is a trade-off between predictability and adaptability. Deterministic workflows fit domains where the workflow is straightforward. LLM orchestration lets you create flexible solutions for problems with no fixed work path.

Key recommendations for developers:

- Define the problem space and check if a single entity can handle it or if it needs distributed intelligence.

- Focus on tool design and selection for any agent system.

- Check scalability, fault tolerance, and maintainability needs.

- Choose deterministic workflows for simplicity and reliability, and use LLM orchestration for flexibility and innovation.

- Monitor and update agent interactions, communication protocols, and orchestrator behavior to match system goals.

- Explore agent self-improvement. Agents can improve their prompts and tool use when given the chance.

By understanding these architectural paradigms and their trade-offs, you can build intelligent systems that are robust, scalable, and well suited to your applications.

## Related content

- [Overview of Customer Intent Agent](/dynamics365/contact-center/administer/overview-customer-intent-agent)  
- [Customer Intent Agent for Voice](/dynamics365/contact-center/administer/set-up-voice-agents-to-use-intents)  
- [Use intent-based suggestions](/dynamics365/contact-center/use/use-intent-suggestions)  
- [Autonomous service agents in Dynamics 365](/dynamics365/contact-center/administer/autonomous-agents-overview)  
- [Automate intent discovery and resolution with Customer Intent Agent - Microsoft Dynamics 365 Blog](https://www.microsoft.com/dynamics-365/blog/it-professional/2025/08/19/automate-intent-discovery-and-resolution-with-customer-intent-agent/)  
