# LLM-Assisted PRA COREP Reporting Assistant

## Project Overview
This project is a prototype for an AI-powered assistant designed to help UK banks navigate the complex world of **COREP regulatory reporting**. 

Reporting analysts often struggle with dense, frequently updated rules in the **PRA Rulebook**. This tool acts as a bridge: it takes a simple financial scenario (like "We have £5M in capital") and automatically identifies which rules apply, which instructions to follow, and exactly where to put the numbers in a reporting template.

## How it Works (The Flow)
The assistant follows a 4-step process to ensure accuracy and transparency:

1.  **Ingestion:** It reads official PRA Rulebooks (.txt), instruction manuals (.txt), and actual COREP Excel templates (.csv).
2.  **Retrieval:** When a user asks a question, the system uses **RAG (Retrieval-Augmented Generation)** to find the most relevant paragraphs and template rows from its database.
3.  **Mapping:** The AI extracts numbers from the user's scenario and maps them into a structured format (Row ID, Column ID, and Template ID).
4.  **Audit Log:** For every number it populates, it provides a "Justification" citing the exact rule paragraph used, making it easy for human auditors to verify the work.



## Key Features
* **Automated Mapping:** Converts natural language questions into structured COREP cell IDs.
* **Validation & Flags:** Automatically flags if data is missing or if the scenario is inconsistent with the rules.
* **Human-Readable Output:** Uses Python (Pandas) to display results in a clean table format that looks like a real reporting extract.
* **Transparency:** Every answer comes with an "Audit Log" for regulatory compliance.

## Tech Stack
* **Python:** The core logic.
* **LangChain:** For building the AI pipeline and "Chain."
* **OpenAI (GPT-4o/Turbo):** The brain that interprets the rules.
* **FAISS:** The vector database used to store and search the regulatory library.
* **Pandas:** For displaying the final report in a clean, aligned table.

## Author's Note
When I first approached this project, I was comfortable with the technical side of RAGs, but the world of PRA Rulebooks and COREP reporting was very new to me. I knew how to make an AI find things from vector stores, but I didn't yet understand what it was looking for or why it mattered to a bank.

To solve this, I spent time looking into the actual flow of regulatory data. I realized that the challenge isn't just searching for text, it’s about connecting three things:

The complex legal language of the Rulebook.
The technical instructions for the templates.
To match the bank's messy data into the template.

I built this prototype to act as a bridge. Instead of just giving a general answer, the assistant focuses on getting things exactly right. It takes a simple description of a bank's situation, searches the database for the specific rules that apply, and then organizes the answer into a clear table that looks just like a real reporting form.

This project was a huge learning for me. It pushed me to move beyond just writing code and actually try to solve a real-world problem. I hope this prototype demonstrates not just my technical skills with LLMs, but also my ability to learn a complex new domain and build something truly useful for it.