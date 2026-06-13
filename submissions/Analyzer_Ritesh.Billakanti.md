# Project Submission Template

Create a new file inside the `submissions/` folder using this naming format:

```txt
Analyzer_Ritesh.Billakanti.md
```

Example:

```txt
ai-sales-copilot_shlok-srivastava.md
```

Copy the template below into your new file and fill in the details.

---

# Project Name

Analyzer 

---

## Attendee Details

**Name:** Ritesh Billakanti
**GitHub Username:** dillu2003
**LinkedIn Profile:** https://www.linkedin.com/in/ritesh-billakanti-8047b9256/
**GitHub Project Repository:** https://github.com/dillu2003/Analyzer_RiteshBillakanti

---

## Problem Statement Selected

Intelligent Slack Knowledge Base


---

## Project Description

What is the project about?
This project is an advanced, AI-powered Single-Document Knowledge Engine. It is an interactive chat and synthesis application that allows users to instantly upload documents, paste raw text, or provide live web URLs (such as dense Wikipedia pages) and have a dedicated, isolated conversation with that specific piece of content.

Who is it for?
It is built for students, researchers, developers, and professionals who need to rapidly extract deep insights, query complex data, or get high-level summaries from massive, text-heavy assets without suffering from information overload.

What problem does it solve?
Traditional AI setups either look at a single short prompt or dump everything into a massive global database where old uploads contaminate new answers. Furthermore, standard web scrapers ingest entire web pages—including headers, footers, sidebars, and massive tables of contents—which paralyzes the AI with "noise." This tool introduces Context Locking, forcing the AI to focus exclusively on the active document while programmatically stripping out background website layout junk.

How does it help the user?
Instead of manually reading through 50-page PDFs or endless Wikipedia entries, users can ingest the source asset in seconds. The UI dynamically locks onto that document's unique ID, enabling users to ask highly targeted questions or trigger an automated, distraction-free summary instantly.

## Approach

How you understood the problem:
I realized that for effective analysis, a user needs an isolated environment for their current task. If a user uploads a document about "Elephants" and then switches to an article about "Horses," the AI shouldn't mix up the facts. The solution required a strict document tracking layer wrapped inside a localized vector search space.

What user flow you designed:

Ingest: The user chooses an ingestion stream (File Upload, Live URL, or Raw Text) via a clean tabbed header component.

Lock-On: The system processes the asset, saves structural metadata, and flags a visible "Active Document" indicator badge above the chat interface.

Interact: The user talks naturally to that specific document.

Command Switch: The user can drop a special slash command (/summarize) directly into the main chat box to instantly pivot the engine from a Q&A machine into a structural summarizer.

What features you decided to build:

Multi-Format Ingestion Pipelines: Specialized loaders for PDFs, Word files, text snippets, and raw HTML scraping.

Metadata-Filtered RAG (Retrieval-Augmented Generation): Rather than searching the entire database, every single vector query is strictly restricted by a database-backed document_id filter.

Heuristically Isolated Summaries: A customized summarization engine that samples the primary informational introduction vectors of an asset, ignoring navigation structures and index menus.

How AI is used in your solution:

Local Embeddings Engine: A Hugging Face transformer model runs locally to convert raw chunks of text into geometric vectors.

Cloud LLM Orchestration: An ultra-fast Llama 3.1 model hosted on Groq is orchestrated via LangChain to act as the reasoning engine, synthesizing responses using only the exact textual context injected at runtime.

What makes your approach useful or different:
It is light, incredibly fast, and achieves complete context isolation. It provides an enterprise-grade RAG pipeline using a hybrid local/cloud architecture that runs seamlessly on a local machine without expensive cloud-vector hosting fees.

## Tech Stack and Tools Used

Frontend: React, Vite, Tailwind CSS, JavaScript (ES6+)
Backend: Python, FastAPI, Uvicorn, LangChain Core, LangChain Community
Database: PostgreSQL (Relational Tracking/Metadata), ChromaDB (Local Open-Source Vector Database)
AI Tools/API: Groq API (Llama 3.1 8B Instant), Hugging Face Embeddings (all-MiniLM-L6-v2)
Cloud/Deployment: Localhost Architecture (Optimized for edge execution and zero cloud computing costs)
Other Tools: Visual Studio Code, Git, Postman, Python Dotenv

## Key Features

List the key features of your project.
Active Context Locking: A dynamic state management system that links the entire frontend chat session to a single vector-isolated document_id.

Noise-Filtering Web Scraper: Integrated WebBaseLoader architecture capable of pulling raw copy directly from live web addresses and parsing it into structured text chunks.

Slash-Command Intent Routing: A smart parser embedded in the message bar that handles text interactions as normal queries but instantly routes /summarize calls to a dedicated, instruction-bounded summary chain.

Asynchronous Fluid UI: Built with real-time feedback loops including processing micro-copy loaders, structural error handling, active document badges, and an automated smooth-scrolling chat history.

## What is Working?

Complete multi-source ingestion pipeline (PDF, Text, and URL web scraping) is fully functional.

Relational database entry handling with PostgreSQL successfully records unique primary keys for every upload.

Text chunk segmentation using RecursiveCharacterTextSplitter correctly matches up vector weights.

Fully localized vector database writes and reads are operational inside the ./chroma_db directory.

The frontend UI completely synchronizes with the backend state, preventing cross-document data bleed during active queries.

## What is Still in Progress?

Enterprise Integration Pipelines: Expanding the automation footprint to hook the ingestion engine directly into ticketing systems like Azure DevOps (ADO) to automatically ingest and execute sprint tickets via AI.

Multi-Channel Distribution: Deploying a custom Slack Bot integration operating on Socket Mode to bring this single-document assistant directly into collaboration workspaces.

Total Cloud Independence: Swapping the cloud-based Groq API for a completely local Ollama setup running Llama 3 models directly on local hardware to completely eliminate internet dependencies and API rate limits for large public demonstrations.

## Screenshots or Demo

Add screenshots, demo video link, or deployed project link if available.

**Deployed Link:**
**Demo Video Link:**
**Screenshots:**

---

## Challenges Faced

Mention any challenges you faced while building this project.

Write your answer here.

---

## Learnings

Mention what you learned while building this project.

Write your answer here.

---

## Future Improvements

Mention what you would improve if you had more time.

Write your answer here.

---

## Final Note

Use this space to add anything else you want mentors, judges, or the community to know about your project.

Write your answer here.
