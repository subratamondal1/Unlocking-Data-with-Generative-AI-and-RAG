# What is RAG (Retrieval Augmented Generation)?
At the center of Artificial Intelligence (AI) is Generative AI and at the center of Generative AI is Retrieval Augmented Generation (RAG). 

RAG uses private data stored in a vector database to augment the capabilities of large language models (LLMs). 

# Advantages of RAG
- RAG improves the Model's `accuracy` and `relevance` by using private data. 
- It increases the `knowledge` of the model beyond the training data `without retraining`. 
- It make the model more `versatile`, `flexible` and `adaptable` to new domains and topics which were never present in the training data.
- It also removes `hallucinations (wrong information)`.
- RAGcan even be applied to `image`, `audio` and `video`.

**Note:** A well-designed RAG Pipeline can remove hallucinations much more easily than when directly using LLMs.

# Challenges of RAG
- RAG is dependent on the quality of the Private Data and the quality of the LLM. (Garbage in Garbage out).
- Need for Data Cleaning and Manipulation.
- `Computational Overhead` as each LLM calll takes few seconds to process and combining them with multiple data processing steps + LLM calls can slow down the entire pipeline.
- **Data Storage Complexity**: RAG (Retrieval-Augmented Generation) increases data storage complexity by dispersing data across various formats and locations, such as vector databases. Integrating and maintaining these data sources with LLMs and vector searches requires significant resources, technical expertise, and infrastructure. 
- **Information Overload**: Managing information overload becomes a challenge, as too much data can be retrieved. Effective `filtering` and `ranking` mechanisms are needed to ensure only relevant information is included in outputs, adding to the complexity and cost.
- **Hallucinations**: The model can generate hallucinations (wrong information) when it cannot find the relevant information in our Private Data in the vector database.

# RAG Vocabulary

## 1. Large Language Model (LLM)
LLMs are generative AI technologies that focus on generating text. Some of the most popular LLMs are:
- OpenAI ChatGPT Models
- Meta Llama Models
- Anthropic Claude Models
- Cohere Models

## 2. Prompting, Prompt Design and Prompt Engineering
- **Prompting**: Sending a query or "prompt" to an LLM.
- **Prompt Design**: The strategy you take to "design" the prompt that you will send to the LLM.
- **Prompt Engineering (technical aspects)**: The art of crafting prompts to improve the LLM's outputs. This involves breaking up complex queries into smaller, more manageable pieces, "engineering" them better, and then combining them back together to achieve superior results.

## 3. LangChain and LlamaIndex
- **LangChain:** RAG + any development that wants to use LLMs within their pipeline.

- **LlamaIndex:** Leading alternative to LangChain that is more focused on more advanced search or retrieval tasks or need to handle large datasets.

## 4. Inference (Prediction)
The process of generating predictions based on given inputs.

## 5. Context Window
A context window is the maximum number of tokens that an LLM can process in a single pass to generate predictions. 

- It's a key parameter of the model architecture and is typically fixed during model training.

For example, if a model has a context window size of 4,096 tokens, it means that the model can process and generate sequences of up to 4,096 tokens. When processing longer texts, such as documents or conversations, the input needs to be divided into smaller segments that fit within the context window. This is often done using techniques such as **sliding windows** or **truncation**.

The size of the context window has implications for the model’s ability to understand and maintain long-range dependencies and context. Models with larger context windows can capture and utilize more contextual information when generating responses, which can lead to more coherent and contextually relevant outputs. However, increasing the context window size also increases the computational resources required to train and run the model.

In the context of RAG, the context window size is essential because it determines how much information from the retrieved documents can be effectively utilized by the model when generating the final response.

## 6. Fine Tuning: FMFT (Full Model Fine Tuning) and PEFT (Parameter Efficient Fine Tuning)

- **FMFT (Full Model Fine Tuning)** is where you take a `foundation model` and train it further to gain new capabilities. You could simply give it new knowledge for a specific domain, or you could give it a skill, such as being a conversational chatbot. `FMFT updates all the parameters and biases in the model`.

- **PEFT (Parameter Efficient Fine Tuning)**, on the other hand, is a type of fine-tuning where you focus only on `specific parts` of the parameters or biases when you fine-tune the model, but with a similar goal as general fine-tuning. The latest research in this area shows that **you can achieve similar results to FMFT with far less cost, time commitment, and data.**

Fine-tuning also helps the LLM to understand your company’s data better, making it better at generating an effective response during the RAG process. For example, if you have a scientific company, you might fine-tune a model with scientific information and use it for a RAG application that summarizes your research. This may improve your RAG application’s output (the summaries of your research) because your fine-tuned model understands your data better and can provide a more effective summary.

## 7. Vector Store or Vector Database?
Both! All Vector Databases are Vector Stores but not all Vector Stores are Vector Databases.

See! There are ways to store vectors that are not full databases. They are simply storage devices for vectors. So to encompass alll possible ways to store vectors, LangChain calls them Vector Stores. And note that not all Vector Stores that LangChain supports are Vector Databases.

## 8. Vectors orEmbeddings (1D List)
A mathematical representation of your data. E.g: [0.123, 0.321, 0.312, 0.231]

They capture semantic information in a format that can be processed by algorithms, facilitating tasks such as similarity search.

When working with vectors for vectorization, there are often hundreds or thousands of dimensions, which refers to the number of floating points present in the vector. Higher dimensionality can capture more detailed semantic information, which is crucial for accurately matching query inputs with relevant documents or data in RAG applications.

# Implementing RAG in AI Applications
- **Customer support and chatbots:** These can exist without RAG, but when integrated with RAG, it can connect those chatbots with past customer interactions, FAQs, support documents, and anything else that was specific to that customer.
- **Technical support:** With better access to customer history and information, RAG-enhanced chatbots can provide a significant improvement to current technical support chatbots.
Automated reporting: RAG can assist in creating initial drafts or summarizing existing articles, research papers, and other types of unstructured data into more digestible formats.
- **E-commerce support:** For e-commerce companies, RAG can help generate dynamic product descriptions and user content, as well as make better product recommendations.
- **Utilizing knowledge bases:** RAG improves the searchability and utility of both internal and general knowledge bases by generating summaries, providing direct answers to queries, and retrieving relevant information across various domains such as legal, compliance, research, medical, academia, patents, and technical documents.
- **Training and education:** RAG can be used by education organizations and corporate training programs to generate or customize learning materials based on specific needs and knowledge levels of the learners. With RAG, a much deeper level of internal knowledge from the organization can be incorporated into the educational curriculum in very customized ways to the individual or role.

# RAG VS Generative AI
If you just log in to ChatGPT and ask questions, that is not the same as implementing RAG. Both ChatGPT and RAG are forms of generative AI, and they are sometimes used together, but they are two different concepts.

RAG (Retrieval-Augmented Generation) enhances Generative AI by retrieving real-time, domain-specific data to improve outputs. It boosts technical support chatbots, automates reporting, generates dynamic product descriptions, and enhances knowledge base searches. RAG also aids innovation scouting by identifying trends and tailors educational content to learner needs, offering more relevant and personalized results compared to traditional generative models.

# RAG VS Fine Tuning
RAG (Retrieval-Augmented Generation) and model fine-tuning are two ways to adapt LLMs to new data. **Fine-tuning** adjusts the model's internal parameters based on new data, permanently altering how it processes inputs. However, it's more effective for specialized tasks (like conversational style) and less reliable for factual recall. Fine-tuning is also expensive. **Input/prompts**, on the other hand, allow the model to access new knowledge for immediate recall, similar to short-term memory. This approach is better for factual recall but is limited by the model's context window size (the amount of data it can process at once). Recent models like ChatGPT 4 have expanded this context window, but it remains a key consideration in choosing between RAG and fine-tuning.

# Interesting Fact

> What about the latest Gemini 1.5 model? It has a 1 million token context window or over 1,000 pages!

As the context windows expand, another issue is created. Early models with expanded context windows were shown to lose a lot of the details, especially in the middle of the text. This issue is also being addressed. The Gemini 1.5 model with its 1 million token context window has performed well in tests called needle in a haystack tests for remembering all details well throughout the text it can take as input. Unfortunately, the model did not perform as well in the multiple needles in a haystack tests. Expect more effort in this area as these context windows become larger. Keep this in mind if you need to work with large amounts of text at a time.

