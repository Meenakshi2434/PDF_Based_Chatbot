# PDF_Based_Chatbot

**Conversational Chatbot - AI/ML Assignment**

Project Overview

This project implements a conversational chatbot that leverages an exhaustive knowledge base to answer user queries accurately and contextually. The chatbot's responses are strictly derived from the content of two provided PDF documents, ensuring that users receive reliable and document-based answers.

**Features**
1. Knowledge Base Integration:

The chatbot loads PDF documents, parses the text, and extracts relevant question-and-answer pairs.
Uses fuzzy string matching to handle variations in user queries and match them to the closest question in the documents.

2. Interactive Chatbot:

The chatbot provides a continuous conversation flow and maintains conversation history.
Users can interact with the chatbot in real-time, with the option to exit the conversation at any point.

3. Keyword-Based Suggestions:

Based on detected keywords in user queries, the chatbot suggests relevant questions from the knowledge base for users to choose from.

4. Source Attribution:

Every response provided by the chatbot is attributed to the specific document it was sourced from for full transparency.

# Setup and Configuration

Prerequisites

Ensure the following Python libraries are installed:

pip install PyPDF2 fuzzywuzzy python-Levenshtein

Development Environment
The chatbot is designed to be run in either Google Colab or locally in Python. Make sure to have the necessary Python environment set up with the required libraries installed.

How to Run the Chatbot

1. Clone the Repository:

git clone <repository-url>
cd <repository-name>

2. Add Your PDF Documents: Place your PDF files (e.g., FINAL_FAQs_June_2018.pdf, Final_FREQUENTLY_ASKED_QUESTIONS_-PATENT.pdf) in the working directory.

3. Run the Python Script: In your terminal or Google Colab environment, run the following:

python chatbot.py

4. Start the Chat: The chatbot will prompt for user queries. Type your questions and receive responses based on the knowledge base.

**PDF Knowledge Base Update Process**
To update the knowledge base:

1. Place the new PDF files into the working directory.
2. The system will automatically parse and extract Q&A pairs from the new documents when re-run.

No extensive reconfiguration is required, making the chatbot adaptable for updates.

**Code Breakdown**
*extract_qa_from_pdf(file_path)*

Purpose: Extracts question-and-answer pairs from the provided PDF documents.

Process:
Reads and parses the text from each page of the PDF.
Uses regular expressions to split text into Q&A pairs.
Creates a dictionary mapping questions to their corresponding answers.

*find_answer_in_docs(query, knowledge_base, threshold=70)*

Purpose: Searches the knowledge base for the closest matching question using fuzzy string matching.

Process:

Loops through each document in the knowledge base.
Uses the FuzzyWuzzy library to find the most relevant question based on similarity to the user query.
Returns the matched question and its answer if the similarity score is above a defined threshold.

*chatbot_response(query)*

Purpose: Handles the chatbot's response logic, including calling find_answer_in_docs to fetch the relevant answer from the knowledge base.

Process:

Takes user input, processes it, and returns a response based on the closest match found in the knowledge base.

*run_chatbot()*

Purpose: Manages the chatbot's interactive session with the user.

Process:

Starts an infinite loop to accept user queries.
The chatbot responds with relevant answers until the user types "exit" to end the session.

# Documentation

The detailed explanation of the chatbot’s query processing, response generation, and knowledge base updating process is provided in the accompanying documentation file. Please refer to the file for more details.

Contributing

If you would like to contribute to this project, feel free to fork the repository, create a new branch, and submit a pull request.

License
This project is open-source and available under the MIT License.
