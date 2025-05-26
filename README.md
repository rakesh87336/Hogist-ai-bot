Here is a suitable README file for your Flask app using the FLAN-T5 model for humorous intent-based responses and knowledge Q&A about Hogist:

---

# Hogist AI Server

A Flask-based AI chatbot server powered by the FLAN-T5 Small model for text-to-text generation. This app provides humorous, intent-driven responses and knowledge-based answers about Hogist, a bulk food aggregator platform.

## Features

- Uses a fine-tuned FLAN-T5 Small model for natural language generation.
- Intent recognition with funny, themed prompts for routes like Home, About, Contact, Features, Menu, and Services.
- Knowledge-based Q&A responses about Hogist's vision, mission, services, pricing, and clients.
- Logs recent requests and displays them on the home page.
- CORS enabled for cross-origin requests.
- Runs locally on `http://localhost:8080`.

## Installation

1. Clone the repository:
   ```bash
   git clone 
   cd 
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download or place the FLAN-T5 Small model locally at `local_flan_t5_small` directory.

Download Link : https://huggingface.co/google/flan-t5-small

## Usage

Run the Flask app:
```bash
python app.py
```

Open your browser and visit:
```
http://localhost:8080/
```

### API Endpoint

- `/bot?query=`  
  Send a GET request with a query parameter to get AI-generated responses.

Example:
```bash
curl "http://localhost:8080/bot?query=about"
```

Response:
```json
{
  "response": "Explain About page like a confused but enthusiastic tour guide lost in his own city.",
  "route": "/about"
}
```

## Code Overview

- **Model and Tokenizer**: Loaded from `local_flan_t5_small`.
- **Pipeline**: PyTorch-based text2text-generation pipeline using FLAN-T5.
- **Intent Map**: Maps keywords to prompts and routes with humorous styles.
- **Knowledge Responses**: Predefined answers for common Hogist-related questions.
- **Logging**: Keeps track of recent requests for monitoring.
- **Flask Routes**:  
  - `/` - Home page showing server status and recent logs.  
  - `/bot` - AI chatbot endpoint.

## Requirements

- Python 3.8+
- Flask
- Flask-CORS
- torch
- transformers
- A GPU is recommended but not required.

## Notes

- The model runs on GPU if available; otherwise, it falls back to CPU.
- Customize `INTENT_MAP` and `KNOWLEDGE_RESPONSES` to add or modify chatbot behavior.
- The server currently runs in debug mode on localhost only.
- Download model and extract to folder local_flan_t5_small and keep the folder in the directory 

## License

MIT License

---

This README provides clear instructions, feature summaries, and usage details tailored to your code.
