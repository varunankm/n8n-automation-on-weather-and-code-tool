# n8n-automation-on-weather-and-code-tool
An AI-powered n8n WhatsApp assistant that uses OpenRouter (DeepSeek), memory, OpenWeatherMap, and a Python code tool to intelligently respond to user messages with live weather data and dynamic code execution.
🤖 AI WhatsApp Weather + Code Assistant (n8n Workflow)

This n8n workflow creates an AI-powered WhatsApp assistant that can:

💬 Receive chat messages

🧠 Remember previous conversations (memory buffer)

🌦️ Fetch live weather data using OpenWeatherMap

🧮 Execute Python code dynamically

📲 Send responses back via WhatsApp

🚀 Features

AI Agent powered by OpenRouter (DeepSeek model)

Short-term conversation memory (last 10 messages)

Weather lookup tool (OpenWeatherMap API)

Python Code execution tool

WhatsApp auto-reply integration

🏗️ Workflow Architecture
1️⃣ Trigger

When Chat Message Received

Starts the workflow when a new message is received.

2️⃣ AI Agent

Uses:

OpenRouter Chat Model (deepseek/deepseek-chat-v3.1)

Simple Memory (buffer window = 10)

Tools:

OpenWeatherMap

Code Tool (Python)

3️⃣ Tools Connected to Agent
🌦️ OpenWeatherMap Tool

Fetches current weather

Inputs:

City (auto-extracted by AI)

Language (auto-detected)

🧮 Code Tool

Executes Python code dynamically

Useful for:

Calculations

Data processing

Logic operations

4️⃣ WhatsApp Node

Sends AI response back to user

Uses:

{{ $json.output }} as message body

🔄 Workflow Flow
Chat Trigger
    ↓
AI Agent
    ↓
(Weather Tool / Code Tool if needed)
    ↓
Send WhatsApp Message
🛠️ Requirements

Before running this workflow, make sure you have:

✅ n8n (Self-hosted or Cloud)

✅ OpenRouter API Key

✅ OpenWeatherMap API Key

✅ WhatsApp Business API credentials

✅ Python enabled in Code Tool

⚙️ Setup Instructions
Step 1: Import Workflow

Open n8n

Click Import Workflow

Upload the JSON file
(Use the exported file: 

weather_code_tool_cleaned

)

Step 2: Configure Credentials

Configure the following credentials:

🔹 OpenRouter

Add API Key

Select model: deepseek/deepseek-chat-v3.1

🔹 OpenWeatherMap

Add your API key

🔹 WhatsApp

Add:

Phone Number ID

Access Token

Recipient number

Step 3: Activate Workflow

Click Activate

Send a message to your WhatsApp bot

The AI will respond automatically

🧠 How It Works

The AI Agent decides:

If the user is asking about weather → Calls OpenWeatherMap tool

If calculation/code is needed → Calls Python Code Tool

Otherwise → Responds normally using LLM

Memory stores last 10 messages for contextual conversation.

📌 Example Use Cases

User:

What is the weather in Chennai?

Bot:

Current temperature in Chennai is 32°C with clear sky.

User:

Calculate 45 * 67

Bot:

The result is 3015.

🔐 Security Notes

Never expose API keys publicly.

Store credentials securely in n8n.

Restrict WhatsApp webhook access.

📈 Future Improvements

Add database logging

Add user authentication

Add multilingual auto-translation

Deploy publicly with webhook URL

👨‍💻 Author

Created by Varun Kmv
Built using n8n + OpenRouter + OpenWeatherMap + WhatsApp API
