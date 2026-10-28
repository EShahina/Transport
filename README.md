# Transport Assistant

A Streamlit chat app that uses the Groq API to answer transportation-related questions. It is designed to help with topics such as public transit, route planning, vehicle care, traffic rules, and road safety.

## Features

- Conversational chat interface built with Streamlit
- Groq-powered responses using the `openai/gpt-oss-120b` model
- Transport-focused system prompt
- Chat history during the current app session
- Clear Chat button
- API key loaded from a local `.env` file

## Requirements

- Windows, macOS, or Linux
- Python 3.10 or later
- A Groq API key

## Setup on Windows

Open PowerShell in the project folder and create/activate a virtual environment:

```powershell
python -m venv nyenv
.\nyenv\Scripts\Activate.ps1
```

Install the project dependencies:

```powershell
python -m pip install -r requirements.txt
```

Create a file named `.env` in the project root and add your own Groq API key:

```dotenv
GROQ_API_KEY=your_groq_api_key_here
```

Get an API key from the Groq Console. Do not include quotes around the value. Never commit or share the real key.

## Run the app

From the project directory, with the virtual environment active:

```powershell
streamlit run app.py
```

Streamlit prints a local URL (typically `http://localhost:8501`) where the app can be opened in a browser.

## Troubleshooting

### `GROQ_API_KEY not found`

Check that `.env` is in the same project folder as `app.py`, that the variable is spelled `GROQ_API_KEY`, and that the file contains a non-empty key. Restart Streamlit after changing the file. An already-set `GROQ_API_KEY` environment variable can take precedence over the `.env` value.

### `401 Invalid API Key`

Groq did not accept the key sent by the app. Check that the key is current, copied correctly, and belongs to the Groq service. Revoke and replace any key that has been exposed, then restart Streamlit. Never paste an API key into source code, screenshots, logs, or chat messages.

### Model or quota errors

Check the Groq Console for account limits and confirm that the model configured in `app.py` is available to your account. The app does not provide live traffic or transit information.

## Security

The `.env` file contains a secret and should remain private. It is excluded from Git by `.gitignore`. If a key has been shared or committed, revoke it and create a replacement immediately.


Live LInk:
https://transport-chatbot.streamlit.app/
