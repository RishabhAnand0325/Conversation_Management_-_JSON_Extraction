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

# Technologies Used

- Python 3

- Groq API for high-speed LLM inference.

- OpenAI Python SDK as the client interface for the Groq API.

- Google Colab as the development and execution environment.

# Setup and Usage

Follow these steps to run the project in your own Google Colab environment.

**1.Clone the Repository (Optional)**
```
git clone https://github.com/your-username/your-repository-name.git
```

**2.Open in Google Colab**

- Go to Google Colab.

- Click on File -> Upload notebook... and select the .ipynb file from this repository.

**3.API Key Configuration**

- You will need a Groq API key to run this notebook. You can get one for free from the Groq Console.

- Important: The notebook will prompt you to enter your API key when you run the setup cell. For better security, it is recommended to use Colab Secrets (Insert -> Add code snippet -> Secrets).

**4.Install Dependencies**

The first code cell in the notebook contains the necessary commands to install the groq and openai libraries. Simply run this cell to install them.
```
!pip install groq openai
```

**5.Run the Notebook**

- Execute the cells sequentially from top to bottom by pressing Shift + Enter.

- The notebook includes detailed explanations and outputs for each step

# Task Breakdown

**Task 1: Managing Conversation History with Summarization**

This task demonstrates how to maintain a memory-efficient conversation.

- A conversation_history list stores all messages.

- After every k turns (e.g., 3), the entire history is sent to a model with a prompt to summarize it.

- The old history is then replaced by a system message containing the summary, followed by the most recent turn to maintain immediate context.

- Helper functions for truncating by turn count and character length are also demonstrated.

**Task 2: JSON Schema Classification & Information Extraction**

This task showcases Groq's powerful function calling feature for structured data extraction.

- A user_details_schema is defined, which tells the model exactly what information to look for (e.g., name, email, age) and its data type.

- By using the tool_choice parameter, we force the model to use our extract_user_info function.

- The model's output is not a conversational reply, but a JSON object containing the arguments for the function, which can be easily parsed and used.
