PDF Query Answering System

This project enables querying the content of PDF documents using natural language. It extracts text, processes it into chunks, performs semantic search using embeddings, and generates human-like responses with a pre-trained text generation model.

Features

PDF Text Extraction: Reads and processes the content of PDF files. Semantic Search: Retrieves the most relevant sections based on user queries. Contextual Responses: Generates natural language answers using a pre-trained GPT-2 model. Customizable Workflow: Easily adjust chunk size, top results, and models. Requirements Python Libraries: openai PyPDF2 transformers numpy API Key: Set your OpenAI API key as an environment variable:

bash Copy code export OPENAI_API_KEY='your_api_key_here' Setup Install dependencies:

bash Copy code pip install openai PyPDF2 transformers numpy Place your PDF file in the working directory.

Update the script to point to your file:

python Copy code pdf_path = "/path/to/your-file.pdf" How It Works Text Extraction: Reads text from the PDF using PyPDF2. Chunking: Splits the text into smaller, manageable parts (default: 500 words). Embedding Creation: Encodes chunks into vector embeddings for semantic similarity search. Query Matching: Finds relevant chunks based on the query using cosine similarity. Response Generation: Uses GPT-2 to create a response based on the retrieved content. Usage Run the Script Place the PDF file in your project directory. Update pdf_path to point to the PDF file. Modify the queries in the script to suit your needs. Sample Queries python Copy code query_1 = "What is the internship?" query_2 = "What is GUI?" Expected Output bash Copy code Response 1: Explanation of the internship section from the document. Response 2: Description of GUI based on document content. Customization Chunk Size: Adjust the chunk_size parameter in the chunk_text function. Top Results: Modify top_k in the retrieve_relevant_chunks function. Text Generation Model: Replace gpt2 with a more advanced or fine-tuned transformer model. Limitations Requires well-structured and extractable text in the PDF. GPT-2 might produce generic responses for highly detailed queries. Query results depend on the quality of the embeddings and the PDF's text content. Future Enhancements Integrate larger language models like GPT-3 for richer responses. Expand support for multiple file formats (e.g., DOCX, TXT). Optimize for faster query processing with larger datasets.
