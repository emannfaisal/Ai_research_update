🤖 AI Research Assistant Agent
Personalized Research Automation using Gemini, n8n, and LangChain
This project is an automated AI Research Assistant that monitors global AI trends, filters them based on a specific user's expertise level, and delivers a curated, simplified brief via email every morning.

🔄 Workflow Logic & Data Flow
The system follows a linear pipeline to move from "Raw Information" to "Actionable Knowledge":

Trigger: A Schedule Node initiates the workflow daily at 7:00 AM.

Ingestion: The RSS Read Node fetches the latest papers and news from Google News/arXiv.

Transformation (JavaScript): A custom Code Node parses the raw XML, filters for specific keywords (LLM, Fine-tuning, etc.), and prepares a clean string of the top 5 relevant papers.

Reasoning (Agentic AI): The LangChain Agent, powered by Google Gemini, receives the filtered list. It acts as a "Senior Researcher" to select the single most relevant paper for a 3rd-year software engineering student.

Delivery: The Gmail Node sends the final analysis directly to the user's inbox.

🧠 Prompt Engineering Mastery
The core value of this project lies in the System Prompt designed for the Gemini Agent. Instead of a generic summary, the prompt uses specific engineering techniques:

Role Prompting: Defining the agent as an "Expert AI Research Assistant."

Context Injection: Feeding the agent specific details about the user's current knowledge (e.g., "Completed Andrew Ng’s ML Specialization").

Constraint Setting: Restricting the agent to pick only one paper to prevent information overload.

Output Shaping: Requiring specific sections: Selection Logic, Simplified Explanation, and Summary.

Prompt Example used in this project: "Select the single most relevant paper... Explain why you chose it... Explain the paper to me... Summarize if it is too long... Use good wording/vocabulary."

🛠️ Tech Stack
Orchestrator: n8n

LLM: Google Gemini (via LangChain Integration)

Languages: JavaScript (for data filtering)

Integrations: RSS/XML, Gmail API, Google News

📂 How to Import
Install n8n on your local machine or server.

Create a new workflow.

Copy the JSON from the workflow.json file in this repo and paste it into the n8n canvas.

Configure your Google Gemini API credentials and Gmail OAuth2 credentials.

Activate the workflow to receive your daily AI digest.



Write custom JavaScript to handle data gaps that standard nodes can't bridge.

Implement Agentic Workflows that make autonomous decisions based on provided context.
