AI-Powered Phishing Email Analyzer (n8n Workflow)
An automated n8n workflow designed to evaluate submitted emails for phishing indicators using Large Language Models (Groq Chat Model) and automatically send notifications or alerts based on the analysis.

📌 Overview
This project automates the detection and analysis of potential phishing emails submitted via a form. Once submitted, an AI Agent powered by Groq analyzes the content, evaluates threat indicators (such as suspicious links, spoofed headers, and manipulative language), and branches the workflow based on the result to notify relevant parties via Gmail.

⚙️ How It Works
[On Form Submission]
         │
         ▼
    [AI Agent] ─── (Powered by Groq Chat Model)
         │
         ▼
     [If Condition]
       │       │
    (True)   (False)
       │       │
       ▼       ▼
   [Gmail 1] [Gmail 2]
Trigger — On Form Submission: Accepts incoming email content, headers, or metadata submitted for analysis.

AI Analysis — AI Agent + Groq Chat Model: Passes the submitted data through an LLM to assess threat levels and output structured phishing probability/reasoning.

Logic Gate — If Node: Evaluates the output from the AI Agent (e.g., checking if the message is flagged as Phishing vs. Legitimate).

Action — Gmail Notification:

True Branch: Sends an alert/report for flagged phishing threats.

False Branch: Sends a safe confirmation or logs non-threat submissions.

🛠️ Prerequisites
n8n (Self-hosted or Cloud instance)

Groq API Key (for accessing fast LLM inference)

Gmail Account / Google OAuth Credentials (for automated email alerts)

🚀 Setup & Installation
Clone or Download the Workflow:

Download the workflow JSON file from this repository.

Import into n8n:

Open your n8n canvas.

Click Import from File or paste the workflow JSON into the canvas.

Configure Credentials:

Groq Chat Model: Add your Groq API key in the node settings.

Gmail Nodes: Authenticate both Gmail nodes with your Google OAuth credentials.

Activate the Workflow:

Test the workflow using the On Form Submission trigger URL.

Toggle the workflow to Active.

🔑 Customization
Prompt Engineering: Modify the prompt inside the AI Agent node to fine-tune phishing detection criteria or adjust output formatting (JSON/Structured Text).

Thresholds: Adjust the criteria in the If node to match your desired confidence threshold for flagging suspicious emails.
