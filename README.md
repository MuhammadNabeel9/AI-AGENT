# AI-AGENT
6 Semester AI Project. The AI Slack Messaging Agent for Text, Audio &amp; Images is a smart automation workflow built with n8n, Slack API, and OpenAI GPT-4o Mini that transforms Slack into an AI-powered assistant capable of understanding and responding to multiple types of user input.


**Project Description**

AI Slack Messaging Agent for Text, Audio & Images

The AI Slack Messaging Agent is an intelligent workflow automation project built using n8n, Slack API, and OpenAI GPT-4o Mini. It enables users to interact with an AI assistant directly inside Slack using text messages, voice recordings, and images. The workflow automatically detects the type of incoming message, processes it through the appropriate AI pipeline, and responds within the same Slack conversation thread, creating a seamless and interactive user experience.

When a user mentions the bot in a Slack channel, the workflow first validates the request to ensure it is not responding to its own messages, preventing infinite response loops. It then routes the incoming message based on its content type using a message router. Depending on whether the message contains text, an audio recording, or an image, the workflow executes a dedicated processing pipeline optimized for that specific input.

For text messages, the assistant processes the user's query using OpenAI GPT-4o Mini. The workflow intelligently determines whether the message is a normal conversation or a request to create a task or to-do list. If the message represents a task, the AI converts it into a structured, professional checklist. Otherwise, it generates a concise and context-aware response to the user's question.

For audio messages, the workflow automatically downloads the voice recording from Slack and transcribes it into text using OpenAI Speech-to-Text. The transcribed content is then processed using the same AI pipeline as text messages, allowing users to communicate naturally through voice while still benefiting from intelligent responses and automatic task detection.

For image uploads, the assistant retrieves the image from Slack, downloads it securely, and analyzes it using OpenAI Vision. The AI identifies objects, scenes, and visible information within the image and generates a descriptive response that is sent back to the original Slack thread. This enables users to ask questions about screenshots, diagrams, documents, photographs, or other visual content directly within Slack.

The workflow is designed using n8n's low-code automation platform, making it easy to understand, customize, and extend. Its modular architecture allows developers to integrate additional services such as Google Calendar, Notion, Jira, CRM systems, databases, Retrieval-Augmented Generation (RAG), memory modules, and other AI-powered business applications. This makes the project suitable for workplace productivity, team collaboration, customer support, knowledge management, and enterprise automation.

**Features**

AI-powered Slack assistant

Responds to Slack @mentions

Supports intelligent text conversations

Accepts and processes voice recordings
Automatic Speech-to-Text transcription
Supports image uploads
AI-powered image understanding using OpenAI Vision
Context-aware responses using GPT-4o Mini
Automatic task and to-do list detection
Converts task requests into structured checklists
Replies inside the original Slack thread
Smart message routing based on input type
Prevents bot self-replies and infinite loops
Handles unsupported message types gracefully
Built using n8n's visual workflow automation
Easy to customize and extend
Suitable for workplace productivity and business automation
Low-code solution requiring minimal programming knowledge
