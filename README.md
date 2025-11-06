# 💬 Simple Chatbot using OpenAI API

A lightweight **Python-based chatbot** that uses the **OpenAI Chat Completions API** to have intelligent and context-aware conversations.
This project demonstrates how to integrate **Large Language Models (LLMs)** like GPT into a simple command-line interface for interactive dialogue.

---

## 🚀 Features

* 🧠 AI-powered responses using OpenAI’s GPT models
* 💬 Maintains conversation context across multiple turns
* ⚙️ Easy to customize chatbot personality and behavior
* 🔒 Secure API key handling through environment variables
* 🪶 Minimal and beginner-friendly Python code

---

## 🛠️ Technologies Used

* **Language:** Python 3.8+
* **Library:** `openai` (latest version)
* **Model:** GPT-4o-mini *(can be replaced with GPT-4o or GPT-3.5-turbo)*
* **Environment Variables:** For storing the API key securely

---

## 📦 Installation

1. **Clone this repository:**

   ```bash
   git clone https://github.com/your-username/simple-openai-chatbot.git
   cd simple-openai-chatbot
   ```

2. **Install dependencies:**

   ```bash
   pip install openai
   ```

3. **Set your OpenAI API key:**

   ```bash
   export OPENAI_API_KEY="your_api_key_here"  # macOS / Linux
   setx OPENAI_API_KEY "your_api_key_here"    # Windows
   ```

---

## 💻 Usage

Run the chatbot script:

```bash
python chatbot.py
```

Sample Output:

```
Simple Chatbot (type 'exit' to quit)

You: Hello!
Assistant: Hi there! How can I help you today?
```

Type your messages, and the assistant will respond intelligently.
Type `exit` or `quit` to end the conversation.

---

## 📘 Code Overview

```python
from openai import OpenAI

client = OpenAI(api_key="Your API Key")

print("Simple Chatbot (type 'exit' to quit)\n")
messages = [{"role": "system", "content": "You are a helpful assistant."}]

while True:
    user = input("You: ")
    if user.lower() in {"exit", "quit"}:
        print("Goodbye!")
        break

    messages.append({"role": "user", "content": user})
    reply = client.chat.completions.create(model="gpt-4o-mini", messages=messages).choices[0].message.content
    print("Assistant:", reply)
    messages.append({"role": "assistant", "content": reply})
```

---

## 🧩 How It Works

1. The user enters a message.
2. The message is sent to OpenAI’s Chat Completions API.
3. The GPT model processes it and returns a human-like response.
4. The conversation history is stored so the chatbot remembers context.

---

## 🏁 Conclusion

This simple chatbot shows how easily you can integrate OpenAI’s powerful models into Python applications. It’s a great starting point for building more advanced AI assistants, virtual tutors, or automated helpdesk systems.
