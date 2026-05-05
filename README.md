# LangChain
LangChain for LLM Application Development - examples and guidelines to facilitate learning.

Langchain is an open source library that helps developers bridge the gap between traditional software and LLMs.

It allows developers to support any number of different LLMs and provides over 500 integrations to different language models, vector stores, and tools, as well as supporting memory chains and agents.

# Models, Prompts and Parsers
[L1-Model_prompt_parser.ipynb](notebooks/L1-Model_prompt_parser.ipynb) — Introduces direct OpenAI API calls versus using LangChain's `ChatOpenAI`, `ChatPromptTemplate`, and output parsers. Demonstrates how to use `StructuredOutputParser` to parse LLM responses into typed Python dictionaries with defined schemas.

# Memory
[L2-Memory.ipynb](notebooks/L2-Memory.ipynb) — Covers four types of LangChain conversation memory: `ConversationBufferMemory` (full history), `ConversationBufferWindowMemory` (last k turns), `ConversationTokenBufferMemory` (token-limited), and `ConversationSummaryBufferMemory` (auto-summarized). Each type offers a different tradeoff between context completeness and token usage.

# Chains
[L3-Chains.ipynb](notebooks/L3-Chains.ipynb) — Explores `LLMChain`, `SimpleSequentialChain`, `SequentialChain` (multiple inputs/outputs), and Router Chain for directing queries to domain-specific sub-chains. Uses a product review CSV as a running example to show how chains can be composed for multi-step processing.

# Question and Answer
[L4-QnA.ipynb](notebooks/L4-QnA.ipynb) — Builds a Q&A system over a CSV product catalog using `OpenAIEmbeddings`, `DocArrayInMemorySearch` vector store, and `RetrievalQA` chain. Demonstrates the full pipeline from document loading and embedding to similarity search and answer generation.

# Evaluation
[L5-Evaluation.ipynb](notebooks/L5-Evaluation.ipynb) — Builds a Q&A app over a clothing catalog then evaluates its output using both hard-coded test examples and LLM-generated examples via `QAGenerateChain`. Uses `QAEvalChain` to automatically grade predictions against ground truth answers using an LLM as the evaluator.

# Agents
[L6-Agents.ipynb](notebooks/L6-Agents.ipynb) — Uses LangChain's built-in `CHAT_ZERO_SHOT_REACT_DESCRIPTION` agent with Wikipedia and calculator tools, plus a Python REPL agent for code execution tasks. Also shows how to define custom tools (e.g., a `time` tool) and integrate them into an `AgentExecutor`.

# LangChain Expression Language (LCEL)
[L2-lcel-student.ipynb](notebooks/L2-lcel-student.ipynb) — Introduces LCEL's pipe syntax (`|`) for composing chains of prompts, models, and parsers in a declarative way. Covers `RunnableMap` for parallel inputs, model binding with OpenAI functions, fallback chains, and the interface methods (`invoke`, `batch`, `stream`, `ainvoke`).

# OpenAI function calling
[L1-openai_functions_student.ipynb](notebooks/L1-openai_functions_student.ipynb) — Demonstrates OpenAI's function calling feature, where the model decides to invoke a defined function (e.g., `get_current_weather`) based on user input. Covers `function_call` parameter modes (`auto`, `none`, forced) and how to pass function results back into the conversation.

[L3-function-calling-student.ipynb](notebooks/L3-function-calling-student.ipynb) — Shows how to use Pydantic models with `convert_pydantic_to_openai_function` to define typed OpenAI function schemas inside LangChain. Demonstrates binding functions to models, using them in chains, and letting the model choose between multiple functions (e.g., `WeatherSearch` vs `ArtistSearch`).

# Tagging and Extraction
[L4-tagging-and-extraction-student.ipynb](notebooks/L4-tagging-and-extraction-student.ipynb) — Uses OpenAI function calling via Pydantic schemas to tag text with sentiment/language and extract structured data (e.g., names and ages) from unstructured text. Extends to a real-world use case by splitting a long blog post into chunks and extracting paper references across all segments.

# Tools and Routing
[L5-tools-routing-apis-student.ipynb](notebooks/L5-tools-routing-apis-student.ipynb) — Defines custom LangChain tools using the `@tool` decorator and Pydantic schemas, including a live weather API tool and a Wikipedia search tool. Demonstrates routing where the model selects the appropriate tool based on user input, using `OpenAIFunctionsAgentOutputParser` to handle dispatch and final responses.

# Conversational Agent
[L6-functional_conversation-student.ipynb](notebooks/L6-functional_conversation-student.ipynb) — Builds a stateful conversational agent that maintains chat history using `ConversationBufferMemory` and `MessagesPlaceholder`. Culminates in a Panel-based chatbot GUI combining weather lookup, Wikipedia search, and a custom tool with full multi-turn memory.