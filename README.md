# 🤖 AI WhatsApp Bot (n8n + Ollama)

A fully automated AI-powered WhatsApp bot built using **n8n**, **Ollama (local LLM)**, and **WhatsApp Cloud API** — running completely on local infrastructure (no paid APIs).

---

## 🚀 Features

- 📩 Receives WhatsApp messages via webhook  
- 🧠 Processes messages using local AI (Ollama)  
- 💬 Maintains conversation memory  
- ⚡ Sends instant replies back to WhatsApp  
- 🔒 Runs locally (no external AI cost)  

---

## 🧰 Tech Stack

- **n8n** – Workflow automation  
- **Ollama** – Local LLM (phi3 / tinyllama / llama3)  
- **WhatsApp Cloud API** – Messaging  
- **ngrok** – Public webhook tunnel  

---

## 🏗️ Architecture

📱 User (WhatsApp) → 🌐 Webhook (n8n) → 🔍 IF Node → 🧾 Edit Fields → 🤖 AI Agent → 🧾 Edit Fields (format response) → 📤 WhatsApp API → 📱 Reply to User
                                                                              │
                                                                              ├── 🧠 Memory (chat history)
                                                                              └── 🧠 Ollama Model (local LLM)
                                                                              │
                                                                              ▼

---

## 🧠 How It Works

1. User sends message on WhatsApp  
2. Webhook receives it in n8n  
3. Message + phone number are extracted  
4. AI Agent processes input using Ollama  
5. Memory node keeps conversation context  
6. Response is formatted  
7. WhatsApp API sends reply back  

---

## ⚙️ Setup Instructions

### 1️⃣ Install Requirements

- Install **n8n**
- Install **Ollama** → https://ollama.com  
- Install **ngrok** → https://ngrok.com  

### 2️⃣ Start Services 

# Start Ollama server
ollama serve

# Pull model (choose one)
ollama pull tinyllama
# or
ollama pull llama3

# Start n8n
n8n start

# Start ngrok
ngrok http 5678

### 3️⃣ Configure Webhook

Use your ngrok URL:
https://your-ngrok-url/webhook/webhook-test/whatsapp
Add this to your WhatsApp Cloud API webhook settings.

### 4️⃣ Import Workflow
Open n8n dashboard
Import your workflow JSON
Update:
WhatsApp API Token
Phone Number ID

---

🔐 Environment Variables

Create a .env file:
WHATSAPP_TOKEN=your_token_here
PHONE_NUMBER_ID=your_id_here

⚠️ Never upload real tokens to GitHub.

🧪 Example
User: Hello
Bot: Hi! How can I help you today?

📈 Improvements (Next Steps)
 - 🌦️ Weather API integration
 - 🔍 Web search tool
 - 🗣️ Voice replies (Text-to-Speech)
 - ☁️ Deploy on VPS (24/7 uptime)
 - 📊 Admin dashboard

⚠️ Important Notes
 - Free ngrok URL changes after restart
 - Keep Ollama running in background
 - Use smaller models (tinyllama) for faster response

🙌 Author
 - Pranay Gurjar

⭐ Support
If you like this project:
 - ⭐ Star the repo
 - 🔁 Share it
 - 💬 Give feedback

![Workflow_WhatsApp_Bot](https://github.com/user-attachments/assets/14f860d5-1c1e-4ca5-a283-c15bbe682bfd)
![WhatsApp_Bot_Chat](https://github.com/user-attachments/assets/f206fb30-0511-458b-a598-9061b31ae95b)
