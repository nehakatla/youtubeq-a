# YouTube Video QnA using LLM

## Overview

YouTube Video QnA is a project that leverages the [LangChain Python library](https://python.langchain.com) to perform question and answer (QnA) operations on YouTube video transcripts. The project utilizes various modules from LangChain, including document loaders, text splitters, vector stores, and retrievers, to create a seamless QnA experience for users.

## How It Works

1. **Transcript Retrieval:**
   - The YouTube transcript is obtained using the [LangChain YouTube transcript loader](https://python.langchain.com/docs/integrations/document_loaders/youtube_transcript).
   - The transcribed text is then split into chunks using the [Character Text Splitter](https://python.langchain.com/docs/modules/data_connection/document_transformers/text_splitters/character_text_splitter).

2. **User Embeddings:**
   - The text chunks are converted into embeddings and stored in a vector database. This is achieved using LangChain's [vector stores module](https://python.langchain.com/docs/modules/data_connection/vectorstores/).

3. **Vector Database Indexing:**
   - Data is indexed in the vector database, enabling efficient retrieval. Refer to the [Vector Stores documentation](https://python.langchain.com/docs/modules/data_connection/vectorstores/) for more details.

4. **Query Retrieval:**
   - When a user submits a query, the vector database retrieves relevant documents using [Chroma Self Query](https://python.langchain.com/docs/modules/data_connection/retrievers/self_query/chroma_self_query).

5. **QA Chain Integration:**
   - The retrieved documents are loaded into the Question Answering (QA) Chain, which is documented [here](https://python.langchain.com/docs/use_cases/question_answering/).

6. **Answer Generation:**
   - The user's query is used to fetch the relevant document from the vector database.
   - The document is then fed into the LangChain Language Model (LLM) chain for answer generation. This process is detailed in the [Question Answering documentation](https://python.langchain.com/docs/use_cases/question_answering/).

## Usage

To use YouTube Video QnA, follow these steps:

0. You will need your OpenAI's API key.
1. Install the required dependencies using the provided links.
2. Retrieve the YouTube transcript and save it locally or in a database.
3. Split the transcribed text into chunks using the specified text splitter.
4. Convert text chunks into embeddings and store them in a vector database.
5. Submit user queries to retrieve relevant documents.
6. Load the QA Chain and feed the document to the LLM chain for answer generation.

## Dependencies

- LangChain Python library: [LangChain Documentation](https://python.langchain.com)
- Other dependencies specified in the provided links for loaders, splitters, vector stores, and retrievers.

## License

This project is licensed under the [MIT License](LICENSE).
