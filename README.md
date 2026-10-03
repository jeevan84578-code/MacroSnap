# MacroSnap

MacroSnap is a Streamlit-powered AI nutrition assistant that helps users estimate calories and macros from meal photos or text descriptions. It can chat with the user about food, summarize the day, and send a WhatsApp-ready nutrition summary using Twilio.

## Features

- Upload a meal photo or describe a meal in chat
- Estimate calories and macro breakdowns with Google Gemini
- Maintain a short conversation history for meal tracking
- Send a summarized nutrition update to WhatsApp via Twilio
- Simple onboarding flow for name and phone number

## Tech Stack

- Python
- Streamlit
- Google GenAI (Gemini)
- Twilio

## Project Structure

- `app.py` — main Streamlit app
- `prompts.py` — system and summary prompts
- `requirements.txt` — project dependencies

## Prerequisites

Before running the app, make sure you have:

- Python 3.10+
- A Google Gemini API key
- A Twilio account with WhatsApp messaging enabled

## Setup

1. Clone the repository and open the project folder.
2. Create a virtual environment (optional but recommended):

   ```bash
   python -m venv .venv
   .venv\Scripts\activate
   ```

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Create a `.streamlit/secrets.toml` file in the project root with your credentials:

   ```toml
   GEMINI_API_KEY = "your_gemini_api_key"
   TWILIO_ACCOUNT_SID = "your_twilio_account_sid"
   TWILIO_AUTH_TOKEN = "your_twilio_auth_token"
   TWILIO_WHATSAPP_FROM = "whatsapp:+14155238886"
   ```

   Replace the Twilio number with your actual WhatsApp-enabled Twilio outbound number.

## Run the app

```bash
streamlit run app.py
```

Then open the local URL shown in the terminal, typically:

```text
http://localhost:8501
```

## How it works

- The user enters their name and WhatsApp number on first launch.
- The app creates a Gemini chat session with a nutrition-focused system prompt.
- The user can either send text or upload a meal image.
- Gemini estimates the meal's calories and macros.
- The user can press the WhatsApp button to receive a daily summary via text message.

## Notes

- This project expects secrets to be stored in `.streamlit/secrets.toml` and will not run without them.
- The app uses a simple prompt-based estimation workflow, so results are approximate and intended for casual tracking.
