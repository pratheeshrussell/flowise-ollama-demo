FROM ollama/ollama

ENV OLLAMA_HOST "0.0.0.0"

RUN apt install curl -y

# pull an llm and embedding model
RUN ollama serve & sleep 10 && echo "Pulling model..." && ollama pull gemma:2b
RUN ollama serve & sleep 10 && echo "Pulling embedding model..." && ollama pull all-minilm:l12-v2

COPY entrypoint.sh /entrypoint.sh
# Make the script executable
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]