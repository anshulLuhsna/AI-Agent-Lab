## Testing LLM apps across the development cycle

**Why does testing LLM apps matter?**
To guard against harmful/misleading responses or even embarrassing brand moments caused by LLM apps.

1) **Adding testing to the Design Phase**
These tests are integrated into the fundamental design of the LLM app. 
Applications with built-in error handling can leverage the ability for LLMs to self-correct by
executing tests within the application and feeding errors back to the LLM. 
They promote a "self correction" approach.

Use cases: Self-corrective code generation, Self-corrective RAG (which makes use of LLM-as-judge evaluators)

2) **Adding testing to the Pre-Production Phase** (Also known as offline evaluation)
The goal of pre-production testing is to measure the performance of your application, 
ensuring continuous improvement and catching any regressions on scenarios that you expect to pass. 
The steps are as follows:
*Build a dataset* - Datasets are collections of examples that serve as inputs and (optionally) expected outputs used to evaluate your LLM app. These can built by manual curation, using past application logs, or by synthetic data.
*Define evaluation criteria* - Three types of evaluators: Heuristic evaluators, Human evaluators, LLM-as-Judge evaluators.
*Regression testing* -  AI models show variable performance due to model drift (i.e. degradation due to changes in data
distribution or updates to the model) and sensitivity. As such, regression testing for LLM applications is even more critical and should be done frequently. LangSmith supports these needs with a built-in comparison view.

Use case: Testing agents (Final response/Single step/Agent's trajectory)

3) **Adding testing to the Post-Production Phase** (Also known as online testing)
In post-production, a monitoring system can help detect when your LLM app performance veers off course, allowing you to isolate valuable failure cases.

*Set up tracing*: You’ll need to set up tracing to gain visibility into a
meaningful portion of your production traffic. LangSmith makes this easy to
do and offers insights into not only the user input and application response,
but also all interim steps the application took to arrive at the response. This
level of detail is helpful for writing specific step assertions or debugging
issues later on.

*Collect feedback in production*: Feedback from users, Feedback from LLM-as-Judge evaluators

Use case: Evaluating a RAG application in production.

## Types of AI Agents
AI agents can be classified into several categories, each designed for specific tasks:
Reactive Agents: Operate based on present stimuli without considering past experiences. They are effective for simple, repetitive tasks.
Model-Based Agents: Maintain an internal model of the environment to make informed decisions based on both current and past information.
Goal-Based Agents: Designed to achieve specific objectives by evaluating multiple courses of action.
Utility-Based Agents: Aim to maximize a utility function, assessing actions based on expected outcomes.
Learning Agents: Improve their performance over time by learning from interactions and adapting their strategies accordingly

# Key Components of AI Agents
To build effective AI agents, several core components are essential:
Perception System: Gathers data from the environment using sensors and data sources.
Decision-Making System: Analyzes input data using algorithms and models to determine the best course of action.
Action System: Executes the chosen actions through actuators or other output mechanisms.
Learning Element: Employs machine learning techniques to adapt and improve over time based on feedback from previous actions

## Multi-agent systems (MAS) 
Multi-agent systems are frameworks in which multiple autonomous agents interact or collaborate to perform tasks, solve problems, or achieve specific goals. These systems leverage the capabilities of individual agents to handle complex tasks that would be challenging for a single agent to manage alone.
Key Characteristics of Multi-Agent Systems
Autonomy: Each agent operates independently, making its own decisions based on its objectives and knowledge.
Interaction: Agents communicate and cooperate with one another, which can involve sharing information, negotiating, or competing.
Coordination: Effective coordination among agents is essential for achieving common goals. This can occur through direct communication or through shared environments.
Distributed Problem Solving: MAS are particularly suited for problems that require collective effort, as they can distribute tasks among agents based on their capabilities.

