```markdown
# 🤖 Telegram AI Assistant Bot

This project is a smart Telegram-based AI assistant created using [Make.com (formerly Integromat)](https://www.make.com), OpenAI (or Gemini), and the Telegram Bot API. The assistant supports both voice and text input and can:

- Help plan your day
- Answer general questions
- Understand voice commands using speech-to-text (STT)
- Reply using either text or synthesized voice

---

## 🚀 Features

- 🧠 **AI Agent**: Uses OpenAI/Gemini for intelligent responses
- 🎙️ **Voice Input**: Users can send Telegram voice messages
- 🔊 **Voice Reply**: Replies can be sent as voice using TTS
- 📅 **Day Planner**: Helps you organize your day
- 💬 **Q&A Assistant**: Answers general queries

---

## 🛠️ Tech Stack

| Tool        | Purpose                              |
|-------------|--------------------------------------|
| Make.com    | Scenario automation & flow building  |
| Telegram Bot| User interface via chat              |
| OpenAI/Gemini| AI responses & STT (Whisper API)    |
| Google TTS / ElevenLabs | Converts text to audio   |

---

## 📸 Scenario Overview

1. **Trigger**: Telegram `Watch Updates`
2. **Router**: Classifies intent (e.g., "plan", "question", "voice")
3. **Voice Input**: Converts `.ogg` Telegram message → text via STT (e.g., Whisper)
4. **AI Reply**: Uses OpenAI to generate response
5. **Voice Output** *(Optional)*: Converts text to speech (TTS)
6. **Send Reply**: Telegram message or voice note sent back to user

```

\[Telegram > Watch Updates]
↓
\[Router: Intent Detection]
├── Plan my day → \[OpenAI Planner] → \[Telegram Reply]
├── Ask question → \[OpenAI Q\&A] → \[Telegram Reply]
└── Voice message → \[Whisper STT] → \[Router] → ...

````

---

## 🧑‍💻 How to Use

1. **Create a Telegram bot** with [BotFather](https://t.me/BotFather)
2. **Set up Make.com scenario**:
   - Add Telegram module: `Watch Updates`
   - Use a router to classify commands or text
   - Use HTTP modules for OpenAI/Gemini & Whisper API
   - (Optional) Use HTTP for Google TTS or ElevenLabs
3. **Connect your Telegram bot** using token from BotFather
4. **Test with voice and text inputs**!

---

## 🔐 Environment Variables / Configs

Create a `.env.example` file:

```bash
TELEGRAM_BOT_TOKEN=your_telegram_token
OPENAI_API_KEY=your_openai_key
WHISPER_API_URL=https://api.openai.com/v1/audio/transcriptions
TTS_SERVICE_URL=https://...
````

---

## 📂 Folder Structure (Recommended)

```
/telegram-ai-assistant/
  ├── README.md
  ├── .env.example
  ├── scenario.png
  ├── prompts/
  │     └── planner_prompt.txt
  └── samples/
        ├── voice_input.ogg
        └── voice_reply.mp3
```
