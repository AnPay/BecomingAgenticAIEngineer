# 001 - What is Context Engineering?

## My Understanding

Most people think building AI applications is all about writing better prompts. It's not.

Context engineering is an emerging practice in Agentic AI. It goes beyond prompt engineering by focusing on building the right context before sending a request to a Large Language Model (LLM).

Instead of relying only on a user's prompt, we provide the model with additional information so it better understands the task and can generate more relevant and grounded responses. Good context can help reduce hallucinations and improve the quality of the model's output.

The context may include:

- System instructions
- User request
- Conversation history
- Retrieved documents (RAG)
- Available tools
- Memory
- Agent state
- Structured outputs

### Example

Suppose I ask an AI agent:

> Book me the cheapest flight to Indonesia within the next three weeks.

The agent doesn't simply send this prompt to the LLM.

Instead, it gathers additional context such as my travel preferences from memory, available flight-booking tools, previous conversation history, and any retrieved information needed for the task.

Using this enriched context, the LLM can decide which tools to use, what information to retrieve, and how to complete the booking.

To me, this is what context engineering is—building the right ecosystem of information before the request reaches the LLM.

---

## What I Learned After Review

- Context engineering is broader than prompt engineering.
- It is more accurate to say it **goes beyond** prompt engineering rather than calling it an advanced version.
- Good context helps reduce hallucinations but does not eliminate them.
- Modern AI agents depend on context engineering to coordinate memory, tools, retrieval, and instructions.

---

## Questions I Want to Explore

- How does an LLM decide which tool to call?
- How is context prioritized when the context window is limited?
- What techniques are used to compress or filter context?

---

## References

(To be updated as I study more.)
