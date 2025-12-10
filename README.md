# 🤖 Real-Time AI Avatar Sales Agent

This project is a real-time interactive video agent built for the CrowdWisdomTrading assessment. It uses **n8n** as the backend orchestrator to connect **HeyGen's Streaming Avatar API** with **Google Gemini's AI intelligence**.

## 🚀 Features
* **Real-Time Conversation:** <2s latency using WebRTC and Gemini Flash.
* **Dynamic Context:** Users can define the avatar's persona (e.g., "Car Salesman", "Doctor") via the setup screen.
* **Automated CRM:** Conversations are transcribed, analyzed for sentiment/needs, and saved to Google Sheets automatically.
* **Cost Calculation:** Tracks session duration and estimates API credit usage.

## 🛠️ Tech Stack
* **Orchestrator:** n8n (Self-hosted)
* **Video Generation:** HeyGen Streaming API v2
* **LLM Brain:** Google Gemini 1.5 Flash
* **Frontend:** HTML5 / JavaScript (LiveKit SDK)
* **Tunneling:** ngrok

## 📂 Project Structure
1.  `1_Launcher_Workflow.json`: Handles the frontend hosting and HeyGen session token generation.
2.  `2_Brain_Workflow.json`: Processes user audio (text) and generates AI responses using the defined persona.
3.  `3_Extraction_Workflow.json`: Triggered at session end to analyze the transcript and save data to Google Sheets.

## ⚙️ How to Run
1.  **Import Workflows:** Import the 3 JSON files into your n8n instance.
2.  **Credentials:** Set up credentials for `HeyGen API` and `Google Gemini API` in n8n.
3.  **ngrok Setup:** Run `ngrok http 5678` to expose the n8n webhook.
4.  **Update URL:** Update the `BASE_URL` in the HTML code (inside the Launcher workflow) with your ngrok address.
5.  **Execute:** Activate all workflows and open the launcher URL!
