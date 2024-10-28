Movie Knowledge Graph Chatbot with LangChain and Neo4j

This project is a chatbot application designed to query and interact with a Neo4j graph database populated with movie data. Using LangChain's Cypher-based question-answering capabilities and ChatGroq's LLM, the chatbot responds to complex questions about movies, directors, and actors based on the Neo4j dataset.

Features
Cypher-Based QA with Neo4j: Seamlessly query movie knowledge using natural language, powered by LangChain's GraphCypherQAChain.
ChatGroq LLM Integration: Leverages ChatGroq's Gemma2-9b-It model for advanced language understanding.
Dynamic Movie Data: Includes CSV-based movie data import, enriched with relationships between actors, directors, genres, and movies.


1)Open the Colab Notebook:
Access the notebook from GitHub: .

2)Install Dependencies: Install packages from requirements.txt:
pip install -r requirements.txt

Or, if in Google Colab:
!pip install --upgrade langchain langchain-community langchain-groq neo4j langchain_experimental

3)Set Up Neo4j Database:
Sign in to Neo4j and set up a connection.
Add NEO4J_URI, NEO4J_USERNAME, and NEO4J_PASSWORD to Google Colab's userdata.

Usage
Load the Movie Dataset into Neo4j: Run the movie_query Cypher command to populate Neo4j with movie data:
movie_query = """
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/tomasonjo/blog-datasets/main/movies/movies_small.csv' as row
...
"""
graph.query(movie_query)


Query the Chatbot: Use GraphCypherQAChain to ask questions. Examples:
response = chain.invoke({"query": "Who was the director of the movie GoldenEye"})
print(response)

Dependencies
Neo4j: Stores and retrieves complex movie relationships.
LangChain: Processes and interprets natural language questions.
ChatGroq: Generates nuanced answers based on database contents.
