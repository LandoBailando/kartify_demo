# Kartify Customer Support Assistant

Kartify is an AI-powered customer support app built with Streamlit. It helps customers look up their orders and chat with an assistant about order status, shipping, and support actions.

This project is deployed on **Render** so the app can be viewed online.

## What the app does

- Lets a customer enter a `Customer ID`
- Fetches and lists that customer’s orders from `kartify.db`
- Starts a chat session for a selected order
- Uses LangGraph + OpenAI models to answer order-related questions
- Applies basic guardrails for intent routing and output safety

## Tech stack

- Python
- Streamlit
- LangGraph / LangChain
- OpenAI API
- SQLite (`kartify.db`)
- Docker (for deployment)

## Run locally

### 1) Clone and install dependencies

```bash
git clone <your-repo-url>
cd Kartify
pip install -r requirements.txt
```

### 2) Set environment variable

```bash
export OPENAI_API_KEY="your_api_key_here"
```

On Windows PowerShell:

```powershell
$env:OPENAI_API_KEY="your_api_key_here"
```

### 3) Start the app

```bash
streamlit run app.py
```

## Render deployment

This repo includes:

- `Dockerfile` for containerized deployment
- `.streamlit/config.toml` for proxy-friendly Streamlit settings on Render

When deployed to Render:

- Render builds the Docker image from this repo
- The app starts with the Render-assigned `PORT`
- You can view the app from your Render service URL

Example URL pattern:

`https://<your-service-name>.onrender.com`

## Notes

- Keep your `OPENAI_API_KEY` in Render environment variables (do not hardcode it).
- If you see stale frontend asset errors after redeploy, do a hard refresh (`Ctrl+Shift+R`) or open the app in incognito mode.

