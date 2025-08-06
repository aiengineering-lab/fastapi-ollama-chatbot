# AI Chatbot using FastAPI + Ollama + Mistral

A lightweight, fully local AI chatbot built with **FastAPI**, integrated with **Ollama**, and powered by the **Mistral** language model.

---

## What You'll Learn

* Build an AI chatbot backend with FastAPI
* Run open-source LLMs like Mistral using Ollama
* Create simple API endpoints for chatbot and file uploads
* Understand how to process PDFs and generate AI responses locally

---

## Prerequisites

Make sure you have the following tools installed before starting:

* Python 3.10 or above
* Git
* VS Code or another IDE
* [Ollama](https://ollama.com/download) installed and running

---

## Project Setup Instructions

### Step 1: Clone the Repository

```bash
git clone https://github.com/aiengineering-lab/fastapi-ollama-chatbot.git
cd fastapi-ollama-chatbot
```

### Step 2: Set Up a Virtual Environment

```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### Step 3: Install Python Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Configure Environment Variables

Create a `.env` file in the root folder:

```env
OLLAMA_URL=http://localhost:11434
```

---

## Running the Chatbot

### Step 5: Start the Ollama Model

```bash
ollama run mistral
```

### Step 6: Run the FastAPI Server

```bash
uvicorn main:app --reload
```

Visit the docs at: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

Test Example Input:

```json
{
  "message": "What is artificial intelligence?"
}
```

---

## Code Overview

* `main.py`: FastAPI app with two routes:

  * `/upload-pdf`: Upload and extract text from a PDF
  * `/ask`: Ask questions and get responses using Mistral
* `.env`: Contains Ollama URL config
* `requirements.txt`: List of required Python libraries

---

## API Example (via curl)

```bash
curl -X 'POST' \
  'http://127.0.0.1:8000/ask' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{"question": "What is AI?"}'
```

---

## License

This project is licensed under the MIT License.

---

## Contributions

Contributions and suggestions are welcome. Please open an issue to discuss changes before submitting a pull request.

