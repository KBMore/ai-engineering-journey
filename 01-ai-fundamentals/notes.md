**Que**. What is AI Engineering?

**Ans**: In AI Engineering AI engineer can build intelligence applications using existing AI Models 

**Que**. How is it different from Machine Learning?

**Ans**: Machine learning is where models are trained using mathematical programs, neural network

**Que**.What is an LLM?

**Ans**: LLM is Large Language Model is the process where models are trained on huge dataset to understand and generate human like text

**Que**.Why does an AI application usually have a backend?

**Ans**: To protect api keys, to call database or any other service, to validate request


**Que**.Draw (or describe) the basic AI application architecture we discussed.

**Ans**: In AI Applicaion architetcure user enters prompt which is like information sending to AI chatbox to do particular task or ask any question then AI models take that input process on that text and returns output in LLM form. It uses tokens means is the small pieces of text model processes.


Draw (or describe) the basic AI application architecture we discussed.
In AI Applicaion architetcure user enters prompt which is like information sending to AI chatbox to do particular task or ask any question then AI models take that input process on that text and returns output in LLM form. It uses tokens means is the small pieces of text model processes.

What is an LLM?
An LLM (Large Language Model) is an AI model trained on a vast amount of text data to understand and generate human-like language. It can perform tasks such as answering questions, summarizing, translating, reasoning, and generating content.

What is a token?
A token is the smallest unit of text that an LLM processes. A word may be one token or multiple tokens depending on the tokenizer.

Why doesn't an LLM generate the whole response at once?
An LLM generates responses one token at a time. After predicting each token, it uses the updated context to predict the next token. This process repeats until the response is complete.


How does an LLM generate text?
An LLM receives the input prompt, converts it into tokens using a tokenizer, analyzes the tokens, predicts the next token based on the context, and repeats this process until the response is complete.

What is a context window?
The context window is the amount of information the model can consider while generating a response. It includes the current conversation and other relevant input that still fits within its context window.

What is temperature?
Temperature controls how deterministic or creative the generated response is.

Draw the response-generation flow from today's class.


User
 │
 ▼
React Frontend
 │
 ▼
Backend
 │
 ▼
Claude API
 │
 ▼
Tokenizer
 │
 ▼
Token Analysis
 │
 ▼
Next Token Prediction
 │
 ▼
Repeat Until Complete
 │
 ▼
Streaming Response
 │
 ▼
React UI

Complete Architecture
                USER
                  │
                  ▼
        React Frontend
                  │
      (HTTPS Request)
                  │
                  ▼
             Backend API
     ┌───────────────────────┐
     │ Authentication         │
     │ Authorization          │
     │ Validation             │
     │ Logging                │
     │ Rate Limiting          │
     │ Database Calls         │
     │ Business Logic         │
     └───────────────────────┘
                  │
                  ▼
             Claude API
                  │
     Generates one token at a time
                  │
        (Streaming Enabled)
                  │
                  ▼
             Backend API
                  │
                  ▼
        React Frontend
                  │
                  ▼
        User sees streamed text


        //Module 3

        Update your notes.md with:

**Que** AI Application Architecture:

User
|
React Frontend
|
Backend API
|
DB
|
DB response  + user prompt
|
claude api
|
backend 
|
fronend


Que. Responsibilities of each layer
1. Frontend Layer:
Chat UI
Prompt input
Conversation history display
Markdown rendering
Code block rendering
Copy button
Retry button
Stop generating
Streaming text
Loaders and error messages


2. Backend Layer
Authenticate users
Validate requests
Store API keys securely
Call Claude API
Query databases
Save chat history
Log requests
Apply rate limiting
Stream responses back


3. Database Layer

Databases store facts.

4. Claude API
Understand the prompt
Process the provided context
Generate the response
Stream tokens


Why databases are still needed
Claude is not a database it's a LLM which generate response in natural lanaguage so we need database to store data(company's  or employess confidential) which is called by backend API for ex. 
If user asks he want to purchase car and which is best in 2026  so clalude dont have information about car's related there backend api call will get details about car database the backend will send resposnse from db and user question/prompt to claude then claude will understabd that prompt and generate natural language response and wil send to backend and then backend will send that  to frontned 



