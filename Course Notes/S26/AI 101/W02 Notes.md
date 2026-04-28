## Apr 28 Class
### AI News
- Do we need guardrails for AI?
- Do we need an 'off' button?
- Does AI development/advancement need to be reigned in?

# AI Fundamentals — Key Term Glossary

Prompt given to Claude Sonnet 4.6: 

"Please tell me the most current, industry-standard definitions for the following terms. Format your response in a Markdown format that I can paste into my .md notes file for my AI Fundamentals class.

(List of terms)"

---

## Artificial Intelligence (AI)
The simulation of human intelligence processes by machines, particularly computer systems. AI encompasses a broad range of techniques that enable machines to perform tasks such as learning, reasoning, problem-solving, perception, and language understanding. It is the umbrella field under which machine learning, deep learning, and generative AI all fall.

---

## Large Language Model (LLM)
A Transformer-based neural network trained on massive text datasets to understand and generate human language. LLMs learn the statistical probability distribution of text and are typically trained to predict the next token given all previous tokens. They can perform tasks such as summarizing, translating, reasoning, and generating content. Examples include GPT-4, Claude, and LLaMA.

---

## GPT (Generative Pre-trained Transformer)
A type of LLM developed by OpenAI that uses a decoder-only Transformer architecture to generate text in response to input. "Generative" refers to its ability to create content, "Pre-trained" means it was trained on massive datasets beforehand, and "Transformer" refers to the underlying neural architecture. GPT models are autoregressive — they generate output one token at a time, each conditioned on all previous tokens.

---

## Transformer
The dominant neural network architecture in modern AI, introduced in the 2017 paper *"Attention Is All You Need."* Transformers use attention mechanisms instead of recurrence (RNNs) or convolutions (CNNs), allowing the model to weigh the significance of all parts of the input simultaneously. This enables higher parallelism, shorter training times, and strong performance on language tasks. Nearly all modern LLMs are built on the Transformer architecture.

---

## Neural Network
A computational model loosely inspired by the structure of the human brain, made up of interconnected nodes (neurons) organized in layers. Each connection has a weight that is adjusted during training. Neural networks learn to recognize patterns in data by processing input through multiple layers and adjusting those weights to minimize prediction error. They are the foundation of modern machine learning and deep learning systems.

---

## Layer
A discrete stage of computation within a neural network. Each layer receives input (either raw data or the output of the previous layer), applies a mathematical transformation, and passes the result forward. Networks are composed of an input layer, one or more hidden layers, and an output layer. Deeper networks (with more layers) can learn more complex representations.

---

## Tool (in AI/Agents)
An external function, API, or system that an AI model is given the ability to call during inference. Tools allow AI models to take real-world actions — such as searching the web, querying a database, running code, or sending messages — beyond simply generating text. Tool calling is a core component of agentic AI systems, enabling agents to interact with and affect their environment.

---

## Agent (AI Agent)
An AI system that uses a large language model as its cognitive core to autonomously plan, make decisions, and take sequential actions toward a goal. Agents can call tools, retrieve information, store memory, and adapt their behavior across multi-step tasks. Unlike a simple chatbot that responds to a single prompt, an agent can operate with a degree of autonomy to complete complex, multi-step workflows.

---

## Machine Learning (ML)
A subfield of AI in which systems learn from data to improve their performance on a task without being explicitly programmed with rules. Machine learning algorithms identify patterns in training data and build models that can make predictions or decisions on new, unseen data. It includes supervised, unsupervised, and reinforcement learning approaches.

---

## Token
The basic unit of data that a language model processes. A token can be a whole word, part of a word, a punctuation mark, or even a single character, depending on the tokenizer used. LLMs read input and produce output entirely in tokens. Token count is also how AI providers measure and price usage — the more tokens processed, the higher the cost.

---

## Prompt Engineering
The practice of designing and optimizing the natural language inputs given to an AI model in order to steer its behavior and produce desired outputs. Techniques include setting roles, specifying output format, adding constraints, providing few-shot examples, and using chain-of-thought instructions. Effective prompt engineering can significantly improve the quality, accuracy, and relevance of model responses.

---

## In-Context Learning (ICL)
The ability of a large language model to perform a new task by conditioning on examples or instructions provided within the prompt itself — without any update to the model's weights. The model "learns" what is expected from the context window alone. For example, showing a model three example input-output pairs before asking it to complete a fourth is a form of in-context learning (specifically, few-shot prompting).

---

## Hallucination
A phenomenon in which an AI model generates output that is factually incorrect, fabricated, or nonsensical, yet is presented with apparent confidence. Hallucinations result from the model's statistical nature — it predicts plausible-sounding text rather than retrieving verified facts. This is one of the most significant reliability challenges in deployed LLM systems.

---

## RAG (Retrieval-Augmented Generation)
A technique that combines a language model with an external information retrieval system. When a query is made, relevant documents or data are retrieved from an external source (such as a vector database or knowledge base) and added to the prompt, grounding the model's response in real, up-to-date evidence. RAG helps reduce hallucinations and allows models to answer questions about information beyond their training data.

---

## AGI (Artificial General Intelligence)
A hypothetical form of AI that matches or surpasses human cognitive capabilities across virtually all intellectual tasks — including learning, reasoning, and adapting across diverse domains — rather than being specialized in a narrow area. As of 2025–2026, no system has achieved consensus AGI, though the term is actively debated. Beyond AGI, *Artificial Superintelligence (ASI)* would represent AI that outperforms the best human abilities across every domain.

---

## Tokenizer
The component that converts raw text into tokens before it is passed to a language model. A tokenizer breaks text down into discrete units (tokens) using methods such as Byte Pair Encoding (BPE), WordPiece, or Unigram encoding. Different models use different tokenizers, and the choice of tokenization method can affect model performance. The tokenizer also converts model output tokens back into human-readable text.

---

## Hidden Layer
Any neural network layer that sits between the input layer and the output layer. Hidden layers are where the network learns internal representations of the data — progressively extracting more abstract features at each level. Deep neural networks contain many hidden layers, which is what enables them to model complex, non-linear patterns. The term "hidden" simply means these layers are not directly visible to the user.

---

## Pre-Training
The initial, large-scale training phase in which a model is exposed to a massive, broad dataset (such as text from the internet) and learns general-purpose representations of language or other data. In LLMs, this typically involves next-token prediction across billions of examples. Pre-training produces a *foundation model* — a general base that can then be adapted to specific tasks through fine-tuning.

---

## Fine-Tuning
A subsequent training phase in which a pre-trained model is further trained on a smaller, task-specific or domain-specific dataset to adapt its behavior. Fine-tuning adjusts the model's weights to improve performance on a particular use case — such as following instructions, coding, or medical question answering — while retaining the broad knowledge gained during pre-training. Techniques like LoRA (Low-Rank Adaptation) make fine-tuning more efficient.

---

## Parameter
A numerical value (weight or bias) internal to a neural network that is learned during training. Parameters determine how the network transforms inputs into outputs. During training, parameters are iteratively adjusted via gradient descent to minimize prediction error. Modern LLMs contain billions to