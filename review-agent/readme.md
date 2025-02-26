
# Automated Code Review System

This agent automates the code review process using LangChain and a large language model (LLM) from Groq.  The system generates code, creates test cases, and simulates a review process including managerial approval.  Iteration is built-in; if the manager rejects, the code returns to the development stage.

## Overview

The system operates in three main phases: development (code generation), testing (test case generation), and managerial review (approval/rejection). Each phase uses LLM prompts tailored to the specific task.  The workflow is defined as a directed acyclic graph (DAG) and executed using LangChain, allowing for conditional branching based on the manager's decision.

## Architecture

The architecture is a three-stage pipeline represented as a DAG:

1. **Development:** LLM generates code based on a given description.
2. **Testing:** LLM generates test cases for the generated code.
3. **Managerial Review:** LLM simulates a manager, evaluating the code and providing approval ("Pass" or "Fail").  A "Fail" triggers a loop back to the development stage.


## Tech Stack

* **LangChain:**  Workflow orchestration and LLM interaction.
* **LangGraph:** DAG representation and execution of the code review workflow.
* **Groq:**  Provides the LLM (`qwen-2.5-32b`) for code generation, testing, and review.
* **Python:** Programming language for the entire system.  Libraries used include `typing_extensions`, `langgraph`, `IPython`, `typing`, `operator`, `os`, `dotenv`, and `langchain_groq`.

