# Website Summarizer

This project uses a large language model to automatically summarize the content of any given website. It fetches the text from a URL, processes it, and then uses the Llama 3.2 model via OLLAMA to generate a clean, Markdown-formatted summary.

---

## 🚀 Features

* **Web Content Scraping**: Extracts the main text content from a URL, stripping out irrelevant HTML tags like `<script>`, `<style>`, and `<img>`.
* **AI-Powered Summarization**: Leverages the power of the Llama 3.2 model to understand and condense the website's content.
* **Markdown Output**: The final summary is presented in a clean, readable Markdown format, making it easy to read and use.
* **Modular Jupyter Notebooks**: The code is organized into separate notebooks for configuration, setup, prompts, and the core summarization logic, making it easy to manage and modify.

---

## ⚙️ Prerequisites

Before you begin, ensure you have the following installed:
* Python 3.x
* Jupyter Notebook or JupyterLab
* [OLLAMA](https://ollama.com/) running locally.
* The `llama3.2` model pulled through OLLAMA. You can get it by running:
    ```bash
    ollama pull llama3.2
    ```

---

## 📦 Installation

1.  **Clone the repository or place all the `.ipynb` files in the same directory.**

2.  **Install the required Python libraries:**
    ```bash
    pip install requests beautifulsoup4 notebook
    ```

---

## ▶️ How to Run

1.  **Start the OLLAMA service** to ensure the model is available for API requests.

2.  **Launch Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```

3.  **Open and run the `main.ipynb` notebook.** This notebook is the entry point and will execute the other notebooks in the correct order.

4.  To summarize a different website, simply change the URL in the `display_summary()` function call within the `main.ipynb` notebook and re-run the cell:
    ```python
    # Change the URL to the website you want to summarize
    display_summary("[https://example.com](https://example.com)")
    ```

---

## 🛠️ Project Structure

The project is divided into several Jupyter Notebooks for clarity:

* **`config.ipynb`**: Contains the configuration for the OLLAMA API endpoint and the model name (`llama3.2`).
* **`set_up.ipynb`**: Includes necessary imports (`requests`, `json`, `BeautifulSoup`) and the `Website` class responsible for fetching and parsing the website content.
* **`prompts.ipynb`**: Defines the system and user prompts that are sent to the language model to guide the summarization process.
* **`summarizer.ipynb`**: Contains the core `summarize` function that makes the API call to OLLAMA with the website content and prompts.
* **`main.ipynb`**: The main notebook that runs all other notebooks and calls the final function to display the summary.
