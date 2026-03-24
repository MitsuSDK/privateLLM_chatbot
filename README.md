# 🤖 Private LLM Chatbot

### Local LLM Mobile Chat Interface (Expo + React Native)

A fully local AI chatbot built with React Native (Expo) that connects to a private Large Language Model served via LM Studio using an OpenAI-compatible API endpoint.

No cloud APIs. No external services. 100% local inference.

---
## ‼️ IMPORTANT NOTE

The UI is intentionally vibe-coded: lightweight, minimal, and built quickly to serve experimentation.

This project focuses on AI system integration rather than frontend sophistication.

---

## 🚀 Overview

This project demonstrates how to build a mobile-first conversational AI interface that connects directly to a locally hosted LLM.

The application:

- Runs on mobile (iOS / Android) and web via Expo
- Connects to a local LLM server (LM Studio)
- Uses OpenAI-compatible `/v1/chat/completions` endpoint
- Maintains conversation state
- Handles request / response lifecycle

The objective is to understand how LLM chat systems function at the client level without relying on external APIs.

---

## 🏗️ Architecture

User Input  
↓  
Conversation State (React State)  
↓  
POST Request to Local LLM Server  
↓  
LM Studio (OpenAI-compatible endpoint)  
↓  
Generated Response  
↓  
UI Update  

---

## 🧠 Core Concepts Explored

- Local LLM inference
- OpenAI-compatible API usage
- REST communication with fetch()
- Conversation state management
- Prompt message formatting
- Token temperature configuration
- Error handling for local endpoints
- Mobile-first AI interface design

---

## 🛠️ Tech Stack

### Frontend
- React Native
- Expo
- TypeScript

### Navigation & UI
- expo-router
- react-navigation
- react-native-safe-area-context

### LLM Communication
- fetch API (HTTP POST)
- OpenAI-compatible `/v1/chat/completions` endpoint
- Bearer token authentication

### LLM Runtime (External)
- LM Studio
- Local LLM (e.g., Llama 3.1)

---

## 📦 Dependencies

Main dependencies from `package.json`:

- expo
- react
- react-native
- expo-router
- react-navigation
- react-native-gesture-handler
- react-native-reanimated
- typescript

---

## ⚙️ How It Works

The application sends a POST request to:

http://:1234/v1/chat/completions

With payload:

```json
{
  "model": "lmstudio",
  "messages": [...],
  "temperature": 0.7
}
```
The server responds with:

```json

{
  "choices": [
    {
      "message": {
        "content": "Model response..."
      }
    }
  ]
}
```
---

## 🧩 Conversation Handling

- Messages are stored in React state
- Each message contains:
  - `id`
  - `role` (user / assistant)
  - `text`
- Full conversation history is sent with each request
- Loading state prevents duplicate submissions
- Error handling displays fallback message if the LLM server is unreachable

---

## 🎨 UI Philosophy

The graphical interface was intentionally built in a rapid, vibe-coded approach.

The focus of this project is not frontend sophistication, but LLM infrastructure and client–model interaction.

The UI prioritizes:

- Clean conversation layout  
- Minimalistic design  
- Theme support (light / dark)  
- Functional mobile-first experience  

The goal was to create a lightweight interface to experiment efficiently with local LLM serving.

---

## 🚧 Future Improvements

- Streaming responses
- Token usage tracking
- System prompt configuration
- Conversation memory optimization
- Model selection UI
- Secure token management
- WebSocket-based streaming
- Production-grade error handling

---

## 📌 What This Project Demonstrates

- Understanding of LLM serving infrastructure
- Client-side integration with OpenAI-compatible APIs
- Conversation state management in React Native
- Mobile-first AI interface development
- Private AI system architecture

This project emphasizes system-level understanding over UI complexity.
The response is parsed and appended to the conversation state.
