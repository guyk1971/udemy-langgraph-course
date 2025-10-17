## Project Overview

This project implements a "Reflexion Agent" using LangGraph and LangChain. The agent generates high-quality responses to user questions by following a process of self-reflection and iterative improvement. It leverages the Tavily search engine to gather information and refine its answers.

The core of the project is a LangGraph graph that defines the agent's workflow:

1.  **Draft:** The agent generates an initial draft answer to the user's question.
2.  **Reflect and Critique:** The agent reflects on its own answer, identifying missing information and superfluous content.
3.  **Search:** The agent generates and executes search queries to find additional information to improve its answer.
4.  **Revise:** The agent revises its answer based on the search results and its self-critique.

This iterative process continues until a satisfactory answer is produced or a maximum number of iterations is reached.

## Building and Running

### Dependencies

The project uses `uv` for dependency management. To install the required packages, run:

```bash
uv sync
```

### Environment Variables

The agent requires API keys for OpenAI and Tavily. These should be placed in a `.env` file in the project root:

```
OPENAI_API_KEY=your_openai_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
```

### Running the Agent

To run the agent, execute the `main.py` script:

```bash
uv run python main.py
```

## Development Conventions

*   **Code Style:** The project follows the standard Python PEP 8 style guide.
*   **Type Hinting:** All functions and methods use type hints for clarity and static analysis.
*   **Pydantic Models:** Data structures are defined using Pydantic models in `schemas.py` to ensure data validation and consistency.
*   **LangChain Expression Language (LCEL):** The agent's logic is built using LCEL, which allows for the composition of different components (prompts, models, parsers) into chains.
*   **LangGraph:** The overall workflow is orchestrated using LangGraph, which provides a flexible way to define and execute complex agent behaviors.
