Step-by-step process:
Chat Trigger - The workflow starts when a user sends a message through the n8n chat interface

AI Agent receives the message - The chat input (e.g., "Summarize the report") is passed to an OpenAI-powered agent with specific instructions

Agent has access to two tools:

GetCustomers - Queries a data table containing customer information
GetOrderData - Makes an HTTP request to retrieve order details (prices, quantities, product categories, employee assignments, statuses)
Agent decides which tool(s) to use - Based on the user's question, the AI agent autonomously:

Uses GetCustomers when asked about customer information
Uses GetOrderData when asked about orders, prices, employees, or product categories
May use both tools if needed to answer the question
Memory tracks conversation - A buffer window memory (20 messages) maintains conversation context using the session ID, allowing follow-up questions

Agent responds - The AI formulates a concise answer based on the retrieved data and sends it back through the chat interface

The agent is instructed to only use actual data from the tools and explicitly state when information isn't available rather than making things up.
