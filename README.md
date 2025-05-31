

# My AI Agents

This repository contains a collection of n8n AI agents – each is an n8n workflow that leverages AI to perform a specialized task. Below is a description of each agent, including what it does, how to use it, and an example use case.

## Cold Outreach Agent

**Description:** Automates the entire cold email outreach process using AI. This agent can research and gather leads, draft personalized outreach emails, and send them out autonomously. It essentially handles everything from lead generation to email delivery without manual intervention.

**Usage Instructions:**

* **Setup:** Configure your lead source and email service credentials (e.g. API keys for a leads database or scraper, SMTP/Gmail for sending emails). Also add your OpenAI API key for generating personalized content.
* **Run:** Provide the target criteria for leads (such as industry, role, or keywords). Trigger the n8n workflow (manually or on a schedule) to start the agent. It will then scrape or collect lead contacts, use the AI model to craft individualized email messages for each lead, and send the emails via the configured email node.
* **Output:** The agent logs or outputs the results of sent emails (and can alert you or update a spreadsheet/CRM with the outreach results).

**Example Use Case:** A marketing agency can use this agent to *automatically find potential clients in a specific niche and send each of them a tailored introductory email*. For instance, you could target “manufacturing CTOs in California,” and the agent would find relevant contacts, write a custom email for each highlighting their company’s context, and send it – all hands-free.

## Voice Assistant Agent

**Description:** Enables voice-based interactions with an AI assistant. This agent adds voice input and output capabilities to your workflow, allowing you to speak to the AI and hear it respond. It can convert spoken language to text (speech-to-text) for the AI to understand, and then generate a spoken audio response (text-to-speech) that is delivered back to the user. This creates a hands-free, voice-enabled AI assistant experience.

**Usage Instructions:**

* **Setup:** Integrate a speech-to-text service (for example, using an API like Google Speech or Whisper) and a text-to-speech service (such as Google TTS or ElevenLabs) into the workflow. Ensure API keys for these services are set in n8n. Optionally, configure a phone or microphone input (via Twilio or a webhook that receives audio).
* **Run:** Activate the agent by providing an audio input or a text prompt. For voice input, the agent will transcribe the audio into text for the AI. The AI (powered by an LLM like GPT) processes the query or command. The response text is then sent to the TTS node to produce an audio output.
* **Output:** The agent returns an audio file or streams the spoken response back to you. If using a phone integration, it can even call and play the AI’s answer over a call.

**Example Use Case:** An entrepreneur on the go can *ask the voice assistant agent for a quick update on their schedule or the latest news, and hear the answer out loud*. For instance, you might say, “What’s my first meeting today?” and the agent will reply with the meeting details in a natural-sounding voice. This voice upgrade makes the AI assistant accessible during transit or when multitasking.

## Web Browsing Agent

**Description:** An AI agent augmented with real-time web browsing and data retrieval capabilities. This agent can perform live web searches and fetch information from the internet as part of its reasoning process, making it able to answer questions with up-to-date facts. It connects AI reasoning with real-time web data (via search engine APIs or an external Multi-Tool service), effectively making the agent “smarter than Google Search” for specific queries by combining search results with AI analysis.

**Usage Instructions:**

* **Setup:** Obtain API access for a web search service (such as Google Custom Search, Bing Web Search API, or an MCP server that provides web browsing tools). Configure the API credentials in the n8n workflow. Include an AI Agent node in the workflow and enable tool usage for web search or HTTP requests.
* **Run:** Provide the agent with a user query or prompt that requires external information (e.g. “Find the latest news on renewable energy investments”). The agent will invoke the search tool to retrieve relevant webpages or data in real time. It then uses the LLM to read or summarize those results.
* **Output:** The final answer is compiled by the AI and returned as the agent’s response, often with citations or details from the live data it fetched. The agent can output the answer in text (e.g. via chat interface or email) or any configured format.

**Example Use Case:** A researcher can ask the agent *“What are the most recent developments in electric vehicle technology?”*. The Web Browsing Agent will search online news sources and blogs, then summarize the findings into a concise report. By connecting to real-time web data, the agent provides current information that a static knowledge base might miss.

## Stock Analysis Agent

**Description:** An AI-driven stock market analysis assistant. This agent fetches financial data and news about specified stocks, then analyzes that information using an AI model to produce insights or recommendations. It automates technical and fundamental analysis steps – gathering stock prices, indicators, or recent headlines – and then outputs an easy-to-understand summary or even advice (with appropriate caveats). Users have noted that the agent can now analyze stocks and provide commentary on them.

**Usage Instructions:**

* **Setup:** Configure a financial data API (for example, Alpha Vantage, Yahoo Finance API, or any market data source) with your credentials in the n8n workflow. Include nodes to retrieve stock price history, current price, and relevant news or metrics for a given ticker symbol. Connect an AI (LLM) node that will take this data as input for analysis.
* **Run:** Trigger the agent with a specific stock ticker or company name as input (e.g. “TSLA” for Tesla). The workflow will pull the latest stock information and perhaps recent news articles. The AI node is then prompted with this data to generate an analysis – such as summarizing the stock’s recent performance, notable news, and a general outlook.
* **Output:** The agent returns a written report or answer describing the stock’s status. This could include trends (e.g. “The stock has climbed 5% this week”), key news impacts (“Tesla’s earnings beat expectations”), and even an AI-generated perspective on what it might mean. *Note:* This agent provides information, not financial advice – the insights are only as good as the data and prompts.

**Example Use Case:** An investor could use this agent to *quickly get a summary of a stock before making a decision*. For instance, before market open, you could query “Analyze Apple (AAPL) for me,” and the agent would return a brief analysis of Apple’s recent stock performance and any important events, saving time on manual research.

## Email Assistant Agent

**Description:** An AI email assistant that helps manage and respond to your emails. This agent can read incoming emails, draft replies or summaries, and even send out responses based on natural language commands. It acts like a virtual email secretary: handling routine email tasks or providing you with quick drafts so you don’t have to write from scratch. The agent maintains context as needed (for example, keeping track of an email thread) to produce relevant replies.

**Usage Instructions:**

* **Setup:** Connect the agent to your email inbox through n8n’s email nodes (IMAP or Gmail node for reading emails, and an SMTP or Gmail Send node for sending). Ensure you have the necessary OAuth or email credentials saved in n8n. Provide your OpenAI API key so the AI can generate email text. You may also configure filters or triggers (for example, only trigger on certain labels or senders).
* **Run:** The agent can be triggered by a new email event or by a user command. For instance, when a new email arrives, the workflow can fetch the email content and prompt the AI to draft a suitable reply or a summary. Alternatively, you can send a chat command like “Draft an email to @john thanking him for the meeting” and the agent will compose that email. The AI considers the context (prior conversation or instructions) when generating its output.
* **Output:** The agent produces either a draft reply, a summary of an email thread, or sends the email out, depending on how you use it. Typically, the drafted text is presented for review (you can have the workflow pause for approval) or automatically sent if you trust it. All interactions are logged so you can review what was read or sent.

**Example Use Case:** A busy professional can rely on the Email Assistant to *triage and respond to routine emails*. For example, if your inbox receives frequent customer inquiries, the agent can automatically draft polite, context-aware responses to each new inquiry. You might receive a summary each morning of your unread emails with suggested replies. Using natural language, you could also instruct the agent: “Please reply to the last email from Jane with thanks and let’s schedule a call next week,” and it will generate (and optionally send) that email for you.
