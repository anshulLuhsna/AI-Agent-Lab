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

