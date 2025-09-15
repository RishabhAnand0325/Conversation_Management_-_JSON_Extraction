# Groq API Demo: Conversation Management & JSON Extraction

This project is a Python implementation, designed for Google Colab, that demonstrates two core functionalities of the Groq API using the OpenAI SDK compatibility layer. The primary goal is to showcase advanced chat management and structured data extraction without relying on external frameworks like LangChain or LlamaIndex.

# Objective

The script is built to perform two main tasks:

- Conversation Management: Maintain a running conversation history, implement strategies for truncation, and periodically summarize the chat to keep the context window efficient.

- Structured Data Extraction: Use Groq's function calling capabilities to parse unstructured user chats and extract specific information into a validated JSON object.

# Core Features

- Conversation History Management: Stores user and assistant messages in a structured list.

- Periodic Summarization: Automatically summarizes the conversation after a configurable number of turns (k) to create a condensed memory.

- Customizable Truncation: Includes helper functions to shorten conversation history based on:

  - Number of turns (e.g., keep the last 5 exchanges).

  - Character/word length.

- Structured JSON Extraction: Uses a predefined JSON schema to extract user details (name, email, phone, etc.) from natural language.

- Function Calling with Groq: Leverages the tools and tool_choice parameters to force the model to return structured, validated data
