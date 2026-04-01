# README: Strategic Problem Solver

This project features the **Strategic Problem Solver**, an advanced AI assistant built using the **Agent Development Kit (ADK)**. Unlike basic agents that react immediately, this agent is equipped with the **BuiltInPlanner** to enable multi-step reasoning, trade-off analysis, and structured thinking for complex, "agent-shaped" problems.

## Project Overview
The agent, named **strategic_problem_solver**, is designed to handle tasks that require deep consideration, such as business strategy, technical architecture decisions, or multi-step planning. By leveraging Gemini's native thinking capabilities, it decomposes problems into manageable components before providing a final recommendation.

## Agent Identity & Behavior
The agent is defined by four core parameters that shape its reasoning process:
*   **Model:** Powered by **gemini-2.5-flash** for efficient yet powerful reasoning.
*   **Name:** Identified internally as `strategic_problem_solver`.
*   **Description:** "Solves complex problems using multi-step reasoning and planning."
*   **Instruction:** A comprehensive behavioral blueprint that enforces a systematic 4-step methodology:
    1.  **Understand:** Break the problem down into its core components.
    2.  **Analyze:** Consider multiple approaches and evaluate their respective trade-offs.
    3.  **Plan:** Develop a detailed, step-by-step solution strategy.
    4.  **Execute:** Provide clear, actionable recommendations based on the analysis.

## Key Features

### 1. Built-In Planning
The agent utilizes the `BuiltInPlanner` class to enable multi-step reasoning. This ensures the agent "thinks" through implications, edge cases, and risks before it responds to the user.

### 2. Thinking Configuration
The agent's reasoning depth is customized through `ThinkingConfig`:
*   **Thinking Budget:** Set to **2048 tokens**, allowing for a thorough and thorough analysis of high-complexity queries.
*   **Visible Reasoning:** With `include_thoughts=True`, the agent's internal thought process is visible in the response, providing transparency and aiding in debugging.

### 3. Adaptive Complexity
While optimized for complex tasks, the agent is efficient. It adapts its reasoning depth to the task at hand—providing direct answers for simple factual questions while engaging its full planning suite for multi-faceted problems.

## Prerequisites
*   **Python 3.11 or higher**
*   **Google ADK Framework** (`pip install google-adk`)
*   A valid **API Key** from Google AI Studio (Gemini 2.0+ model required for thinking features)

## Installation & Setup

1.  **Create the Project:**
    ```bash
    adk create problem_solver
    cd problem_solver
    ```

2.  **Configure Environment Variables:**
    Open the `.env` file and add your Gemini API key:
    ```text
    GOOGLE_GENAI_USE_VERTEXAI=0
    GOOGLE_API_KEY=your-actual-api-key-here
    ```
    *Note: Ensure `.env` is added to your `.gitignore` to prevent leaking secrets.*

3.  **Verify the Agent Code:**
    Ensure your `agent.py` includes the `BuiltInPlanner` and the `strategic_problem_solver` logic.

## How to Run

To interact with the agent and observe its internal thinking process in a visual chat interface, run:

```bash
adk web
```

The interface will be available at **http://localhost:8000**.

## Project Structure
*   **`agent.py`:** The main entry point containing the `LlmAgent` definition and its planning configuration.
*   **`__init__.py`:** Required for the ADK framework to discover the agent module.
*   **`.env`:** Secure storage for your Gemini API credentials.
