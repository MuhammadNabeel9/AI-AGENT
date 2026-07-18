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

1 AI-powered Slack assistant

2 Responds to Slack @mentions

3 Supports intelligent text conversations

4 Accepts and processes voice recordings

5 Automatic Speech-to-Text transcription

6 Supports image uploads

7 AI-powered image understanding using OpenAI Vision

8 Context-aware responses using GPT-4o Mini

9 Automatic task and to-do list detection

10 Converts task requests into structured checklists

11 Replies inside the original Slack thread

12 Smart message routing based on input type

13 Prevents bot self-replies and infinite loops

14 Handles unsupported message types gracefully

15 Built using n8n's visual workflow automation

16 Easy to customize and extend

17 Suitable for workplace productivity and business automation

18 Low-code solution requiring minimal programming knowledge

Step 1: Create an n8n Account
Visit n8n Cloud
Sign up or log in.
Click New Workflow.
Step 2: Import the Workflow
Click the ⋮ (three dots) in the workflow editor.
Select Import from File.
Choose your JSON workflow.
Click Open.

After importing, all nodes and their connections will already be connected automatically because the JSON contains the workflow graph.

Step 3: Configure Slack Credentials

Your workflow contains several Slack nodes:

Slack Trigger
Get a File
Send Message
Send Message2
Send Message3
Send Message4
Send Message5
Send Message6

For each Slack node:

Open the node.
Click Credential.
Select Create New Credential.
Connect your Slack Workspace.
Authorize the app.
Save.

If you are using the Slack Trigger, you must also:

Enable Event Subscriptions in your Slack App.
Copy the webhook URL from the Slack Trigger node.
Paste it into your Slack App's Request URL.
Enable the app_mention event.
Reinstall the Slack app to your workspace after changing permissions.
Step 4: Configure OpenAI

Open every OpenAI node:

OpenAI Chat Model
OpenAI Chat Model1
Transcribe Recording
Analyze Image

Then:

Click Credential.
Create a new OpenAI credential.
Paste your OpenAI API key.
Save.
Step 5: Check the Channel ID

Your workflow is configured to work with a specific Slack channel.

Open:

Slack Trigger
Send Message nodes

Replace the existing Channel ID with your own Slack channel.

Step 6: Activate the Workflow

Click the Active toggle in the top-right corner.

When the workflow is active, n8n starts listening for Slack events automatically.

Step 7: Invite the Bot

Inside Slack:

/invite @YourBotName

Invite the bot to the channel where you want it to respond.

Step 8: Test the Workflow
Test Text
@AI What is Artificial Intelligence?

Expected flow:

Slack Trigger
      ↓
Check User
      ↓
Message Router
      ↓
Text Pipeline
      ↓
Basic LLM Chain
      ↓
Text Classifier
      ↓
Slack Reply
Test Voice

Upload a voice message while mentioning the bot:

@AI
(voice message)

Flow:

Slack Trigger
      ↓
Message Router
      ↓
Download Audio
      ↓
Transcribe Recording
      ↓
Basic LLM Chain
      ↓
Text Classifier
      ↓
Slack Reply
Test Image

Upload an image:

@AI What is shown in this image?

Flow:

Slack Trigger
      ↓
Message Router
      ↓
Get File
      ↓
Download Image
      ↓
Analyze Image
      ↓
Slack Reply
Step 9: Verify Each Node

Open each node and ensure there are no red warning icons. Confirm:

Slack nodes have valid Slack credentials.
OpenAI nodes have a valid API key.
The Slack channel ID is correct.
The Slack Trigger webhook is verified.
The workflow is Active.
Complete Workflow Flow
User mentions bot in Slack
           │
           ▼
     Slack Trigger
           │
           ▼
 Check User & Chat ID
           │
           ▼
     Message Router
      ┌────┼─────┐
      │    │     │
      ▼    ▼     ▼
    Text Audio Image
      │    │     │
      ▼    ▼     ▼
  LLM  Speech  Vision
      │    │     │
      └────┴─────┘
           │
           ▼
  Task Detection (if needed)
           │
           ▼
 Reply in Slack Thread
