
# LLM Debate Simulation with Ollama

## Introduction
This project demonstrates a simple LLM debate simulation using Ollama. It sets up an Ollama server, pulls various large language models (LLMs), and orchestrates a debate between them with a 'judge' LLM providing evaluation and feedback.

## Features
-   **Ollama Setup**: Automated installation and server startup for local LLM execution.
-   **Model Management**: Easily pull and manage different LLM models via Ollama.
-   **Debate Topic Generation**: A 'judge' LLM generates a humorous and engaging topic for the debate.
-   **Debater Argument Generation**: A 'debater' LLM crafts witty and logically sound arguments on the given topic.
-   **Debate Judging**: The 'judge' LLM provides funny, critical feedback and scores the debater's arguments.
-   **Flexible Configuration**: Easily switch between different LLMs for the debater and judge roles, and customize their system prompts.

## Setup and Prerequisites
To run this notebook, you need:

1.  **Google Colab Environment**: The notebook is designed to run in Google Colab.
2.  **Ollama**: The `ollama` CLI tool is installed and its server is started in the notebook.
3.  **Python `ollama` Client**: The Python library for interacting with Ollama is installed.
4.  **Ollama Models**: Specific LLM models (`deepseek-r1:1.5b`, `llama3.2:1b`, `qwen3:0.6b`) are pulled and ready for use.

### Installation Steps (handled by the notebook):
-   `!sudo apt-get install zstd`
-   `!curl -fsSL https://ollama.com/install.sh | sh`
-   Run `subprocess.Popen(["ollama", "serve"])` to start the server.
-   `!ollama pull <model_name>` for desired models.
-   `!pip install ollama`

## Usage
1.  **Run all cells sequentially**: Execute each cell in the notebook from top to bottom.
2.  **Observe the output**: The notebook will first set up Ollama and download models. Then, it will:
    -   Print the generated debate topic.
    -   Display the debater LLM's arguments.
    -   Show the judge LLM's humorous feedback and scoring.

## Models Used in the Simulation
-   **`model_debater`**: `deepseek-r1:1.5b` (Configured to be argumentative and snarky).
-   **`model_judge`**: `llama3.2:1b` (Configured to be polite, courteous, and provide funny judgments).
-   **`qwen3:0.6b`**: Also pulled, but not directly used in the provided debate logic, available for experimentation.

## Customization
-   **Change Models**: Modify the `model_judge` and `model_debater` variables in the cell to use other available Ollama models.
-   **Adjust Prompts**: Experiment with the `system_prompt_judge` and `system_prompt_debater` variables to alter the personalities and instructions for the LLMs.
-   **New Debaters/Judges**: You can define additional `system_prompt` variables and associated model configurations to introduce more participants or different judging criteria.

## Potential Enhancements
-   Implement a multi-round debate structure.
-   Add a scoring mechanism that dynamically updates.
-   Integrate more complex judging criteria.
-   Allow user input for debate topics or arguments.
"""
