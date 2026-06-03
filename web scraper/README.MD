```markdown
# Website Summarizer: Tyrion Lannister's Wit on Web Content

This project presents a novel approach to website summarization, channeling the unparalleled wit and snark of Tyrion Lannister from Game of Thrones. It leverages a local Large Language Model (LLM) – specifically `llama3.2:1b` – powered by Ollama within a Google Colab environment. The system scrapes website content, then instructs the LLM to provide a summary as if Tyrion himself were reporting to the Small Council, complete with his characteristic humor, sarcasm, and disdain for corporate speak.

## Features

- **Web Content Extraction**: Skillfully fetches and cleans text content from any given URL, stripping away the navigational chaff.
- **Local LLM Integration**: Operates a private LLM (Ollama with `llama3.2:1b`) directly within the Colab realm, ensuring your secrets are safe... for now.
- **Tyrion Lannister Persona**: Custom-crafted system and user prompts compel the LLM to adopt Tyrion's voice, wit, and perspective.
- **OpenAI API Compatibility**: Communicates with Ollama through the `openai` Python client – a convenient bridge between worlds.

## Technologies Used

- **Python 3**: The very language our scheme is written in.
- **Google Colab**: The convenient tower from which we launch our ravens (the notebook).
- **Ollama**: Our loyal (and local) maester, serving up LLMs.
- **`llama3.2:1b`**: A respectable, if somewhat smaller, dragon to do our bidding.
- **`BeautifulSoup4`**: The tool we use to strip the robes off a website and see its true form.
- **`requests`**: Our trusty messenger to fetch scrolls (webpages).
- **`openai`**: The common tongue for speaking with our Ollama model.

## Setup and Running on Google Colab

To unleash Tyrion's wisdom upon the web, follow these steps in your Google Colab environment:

1.  **Open the Notebook**: Begin by opening this `.ipynb` file in Google Colab.

2.  **Install `zstd`**: A small, but crucial, provision for our Ollama operations.
    ```python
    !sudo apt-get install zstd
    ```

3.  **Install Ollama**: Summon the Ollama server to your Colab domain.
    ```python
    !curl -fsSL https://ollama.com/install.sh | sh
    ```

4.  **Start Ollama Server**: Awaken the server in the background. We afford it a moment to stretch its digital limbs before tasks begin.
    ```python
    import subprocess
    import time

    process = subprocess.Popen(["ollama", "serve"])
    print("Waiting for Ollama server to start...")
    time.sleep(10) # Adjust as needed, a few moments can prevent a costly misunderstanding.
    print("The 'ollama serve' process is running in the background and should be ready.")
    ```

5.  **Pull the LLM Model**: Command Ollama to acquire the `llama3.2:1b` model.
    ```python
    !ollama pull llama3.2:1b
    ```

6.  **Install Python Ollama Client**: Ensure our Python interpreter can properly address Ollama.
    ```python
    !pip install ollama
    ```

7.  **Import Libraries and Define Functions**: Execute the cells that import our necessary scrolls and define our schemes (`fetch_website_contents`, `messages_for`, `summarize`, `display_summary`).

8.  **Summarize a Website**: Now, present a website to Tyrion and await his judgment.
    ```python
    display_summary("https://github.com/karan-singhh")
    ```
    *Replace the URL with any chronicle you wish for Tyrion to dissect.*

## Output Example

The output will be a brief, cutting, and amusing summary, delivered straight from the mind of Tyrion Lannister:

```markdown
"Ah, another GitHub profile. So much talk of 'open source' and 'collaboration,' yet I see no dragons or schemes for the Iron Throne here. A collection of digital scrolls, no doubt filled with endless lines of code – a task fit for a maester, not a Lannister of renown. Still, it appears one 'karan-singhh' has seen fit to brandish his digital prowess. Impressive, if you're into such things."
```

## Future Improvements / Considerations

-   **More Robust Server Check**: The `time.sleep()` is a crude measure, like trusting a Dothraki to stand guard. A more refined method to confirm Ollama's readiness would be prudent.
-   **Enhanced Error Handling**: As with any grand scheme, things can go awry. More robust handling of network woes and API failures is necessary to avoid unpleasant surprises.
-   **Model Versatility**: The ability to easily swap between different LLMs would provide more tools in our arsenal.
-   **Interactive Interface**: To truly impress the Small Council, a more presentable interface (perhaps a modest web app) would serve well.
```
