# Groq API Demo: Conversation Management & JSON Extraction

This project is a Python implementation, designed for Google Colab, that demonstrates two core functionalities of the Groq API using the OpenAI SDK compatibility layer. The primary goal is to showcase advanced chat management and structured data extraction without relying on external frameworks like LangChain or LlamaIndex.

# Objective

The script is built to perform two main tasks:

- Conversation Management: Maintain a running conversation history, implement strategies for truncation, and periodically summarize the chat to keep the context window efficient.

- Structured Data Extraction: Use Groq's function calling capabilities to parse unstructured user chats and extract specific information into a validated JSON object.
