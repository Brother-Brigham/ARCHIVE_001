## Apr 28 Class
 **AI News**
- Do we need guardrails for AI?
- Do we need an 'off' button?
- Does AI development/advancement need to be reigned in?

## Apr 30 Class
- Directives of using AI in this course:
	- Encouraged to use it as much as possible. You are responsible for what it generates.
- 



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
A numerical value (weight or bias) internal to a neural network that is learned during training. Parameters determine how the network transforms inputs into outputs. During training, parameters are iteratively adjusted via gradient descent to minimize prediction error. Modern LLMs contain billions to trillions of parameters — the parameter count is often used as a rough proxy for model capacity.

---

## Deep Learning
A subfield of machine learning that uses artificial neural networks with many layers (hence "deep") to learn representations of data. Deep learning has driven breakthroughs in image recognition, speech processing, and natural language understanding. LLMs are a product of deep learning — specifically, deep Transformer architectures trained at massive scale.

---

## Supervised Learning
A machine learning approach in which a model is trained on a labeled dataset, where each training example consists of an input paired with the correct output (a label). The model learns to map inputs to outputs by minimizing the error between its predictions and the true labels. Examples include image classifiers trained on labeled photos, or spam filters trained on labeled emails.

---

## Unsupervised Learning
A machine learning approach in which a model is trained on data *without* labels, and must discover structure, patterns, or representations on its own. Common tasks include clustering (grouping similar data), dimensionality reduction, and anomaly detection. Pre-training LLMs on unlabeled internet text is technically a form of self-supervised learning — a closely related paradigm.

---

## NLP (Natural Language Processing)
A branch of AI focused on enabling computers to understand, interpret, and generate human language. NLP encompasses tasks such as text classification, machine translation, sentiment analysis, named entity recognition, question answering, and text generation. Modern NLP is dominated by Transformer-based LLMs, which have achieved state-of-the-art performance across nearly all language benchmarks.

---

## Generative AI
A class of AI models designed to generate new content — such as text, images, audio, video, or code — that resembles human-created content. Generative AI models learn patterns from large training datasets and use that knowledge to produce novel outputs in response to prompts. LLMs like GPT and Claude are examples of generative AI for text; diffusion models are used for image generation.

---

## Attention Mechanism
A core component of Transformer architecture that allows a model to weigh the relevance of different parts of the input when processing each element. Rather than treating all words equally, the attention mechanism lets the model focus on the most contextually relevant tokens — for example, connecting a pronoun back to the noun it refers to. The *self-attention* variant allows the model to consider relationships across all positions in the input simultaneously, enabling much richer contextual understanding than earlier architectures.

---

## Training
The process by which a machine learning model learns from data. During training, the model is repeatedly shown examples, makes predictions, and then has its internal parameters (weights) adjusted — via an optimization algorithm like gradient descent — to reduce the error between its predictions and the correct answers. Training large models requires enormous computational resources, primarily GPUs, and can take days to months.

---

## GPU (Graphics Processing Unit)
A hardware component originally designed for rendering graphics that has become the backbone of modern AI training. GPUs can perform thousands of simple mathematical operations in parallel, making them far more efficient than CPUs for the matrix multiplications that neural networks require. NVIDIA currently dominates the AI GPU market with chips such as the H100 and Blackwell series.

---

## Dataset
A structured collection of data used to train, validate, or evaluate a machine learning model. Datasets can consist of text, images, audio, video, structured tables, or other data types. The quality, size, and diversity of a dataset are among the most important factors determining a model's capabilities and limitations. Common LLM training datasets include web crawls (Common Crawl), books, Wikipedia, and curated code repositories.

---

## Gradient Descent
The core optimization algorithm used to train neural networks. During training, gradient descent computes the gradient (the direction and magnitude of error) of the loss function with respect to each model parameter, then adjusts the parameters in the opposite direction of the gradient to reduce error. The process iterates across the entire training dataset until the model's predictions are sufficiently accurate. Variants include stochastic gradient descent (SGD) and Adam.

---

## Temperature
A parameter that controls the randomness and creativity of a language model's output during generation. Temperature values typically range from 0 to 1 (some models extend to 2). A low temperature (e.g., 0–0.3) makes the model more deterministic and predictable, favoring the most likely tokens. A high temperature (e.g., 0.7–1.0) introduces more randomness, producing more varied and creative — but potentially less accurate — outputs.

---

## Emergent Behavior
Unexpected or unpredictable capabilities that arise in AI models as they scale in size or are trained on more data — behaviors that were not explicitly trained for and could not easily be predicted from smaller models. For example, large language models have been observed to spontaneously develop abilities in arithmetic, multi-step reasoning, and code generation at certain scales. Emergent behavior is an active area of AI research and debate.

---

## Context Window
The maximum amount of text (measured in tokens) that a language model can process at one time — effectively the model's working memory. Everything the model "knows" about the current conversation or task must fit within this window. A larger context window allows the model to consider more prior text when generating a response. Modern LLMs range from tens of thousands to over a million tokens in their context windows.

---

*Last updated: April 2026 | AI Fundamentals Class Notes*