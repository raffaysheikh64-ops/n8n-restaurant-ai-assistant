<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ef05073c-3660-4272-a61d-ecb72aa06620" /># 🍔 Database-Free AI Restaurant Assistant (n8n + HTML Frontend)

A lightweight, blazing-fast, and cost-effective AI Customer Support Chatbot built for **"Taste of Lahore"** restaurant. This project utilizes a zero-overhead architecture—meaning it requires **no external database** or complex RAG pipelines. Instead, it leverages highly optimized static prompting and prompt caching via OpenAI to deliver instant, accurate responses at a fraction of a cent.

The chatbot seamlessly handles menu inquiries, hours of operation, location details, and reservation inquiries in both **English and Urdu**.

---
## 🛠️ System Architecture Diagram

![n8n Chatbot Workflow Canvas](restaurant-chatbot.png)

## 🚀 Features

*   **Zero-Database Architecture:** Operates entirely through structured system prompt engineering within n8n.
*   **Bilingual Support:** Automatically detects and responds in the user's input language (Urdu or English).
*   **Custom HTML Frontend Widget:** Includes a clean, responsive web user interface featuring real-time typing indicators and a modern look.
*   **Upwork/Client Ready:** Perfect foundation for pitching automated customer service funnels to local or international restaurants.

---

## 🛠️ Tech Stack

*   **Backend Automation:** [n8n](https://n8n.io/)
*   **LLM Engine:** OpenAI (`gpt-4o-mini`)
*   **Frontend:** Vanilla HTML5 / CSS3 / JavaScript (Fetch API)

---

## 📦 System Architecture

The workflow consists of 3 streamlined nodes:
1.  **Webhook Node (POST):** Receives the user message payload from the frontend interface.
2.  **Message a Model Node:** Processes the request using a compressed static data prompt containing the restaurant's complete menu, hours, and reservation rules.
3.  **Respond to Webhook Node:** Shoots the generated text response straight back to the UI.

---

## 🚀 Setup Instructions

### 1. Backend Setup (n8n)
1. Import the provided `workflow.json` file into your n8n instance.
2. Connect your **OpenAI API** credentials to the *Message a Model* node.
3. Save the workflow and toggle it to **Active** in the top right corner.
4. Copy the **Production Webhook URL** from the Webhook node.

### 2. Frontend Setup (HTML)
1. Open the `index.html` (or your chatbot widget HTML file) in a code editor.
2. Locate the JavaScript configuration block near the bottom:
   ```javascript
   // REPLACE THIS WITH YOUR OWN N8N PRODUCTION WEBHOOK URL
   const WEBHOOK_URL = 'YOUR_N8N_PRODUCTION_WEBHOOK_URL_HERE';
