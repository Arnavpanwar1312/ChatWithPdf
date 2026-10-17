# Chat with PDF Notes System

A simple Flask web app that lets you upload a PDF, process it locally, and ask questions about its contents using a local GPT4All language model and FAISS vector search.

## Features

- Upload a PDF from the browser
- Extract text from the uploaded document
- Split the document into searchable chunks
- Generate embeddings with Hugging Face sentence-transformers
- Store vector data with FAISS for semantic retrieval
- Ask natural-language questions about the PDF content
- Get answers in a chat-style web interface

## Tech Stack

- Python 3.10
- Flask
- LangChain
- FAISS
- Hugging Face Transformers
- GPT4All
- PyMuPDF

## Project Structure

```text
.
├── app.py                 # Flask app and PDF chat logic
├── requirements.txt       # Python dependencies
├── runtime.txt            # Python runtime version
├── models/                # Local GPT4All model files
├── static/                # CSS assets
├── templates/             # HTML templates
├── uploads/               # Uploaded PDFs
└── README.md              # Project documentation
```

## Prerequisites

- Python 3.10
- pip
- A local GPT4All model binary

## Setup

1. Open a terminal in the project root.
2. Create and activate a virtual environment:

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Download the GPT4All model and place it in the `models` folder.

The app expects a file such as:

```text
models/ggml-gpt4all-j-v1.3-groovy.bin
```

You can download the model from the official GPT4All release page or the model distribution source you prefer, then copy it into the `models` directory.

## Run the App

```bash
python app.py
```

Then open:

```text
http://127.0.0.1:5000
```

## How to Use

1. Open the app in your browser.
2. Upload a PDF file.
3. Wait for the app to process and index the document.
4. Type a question in the chat box.
5. The app will retrieve the most relevant content and generate an answer based on the PDF.

## Notes

- This project uses a local model, so it may require more CPU and memory depending on the document size.
- If the model file is missing, the upload step will fail when the app tries to initialize the language model.
- The app currently stores uploaded files in the `uploads/` folder and keeps the chat memory in the server session.

## License

This project is provided for educational/demo purposes.
