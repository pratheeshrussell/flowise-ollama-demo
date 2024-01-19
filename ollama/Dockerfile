FROM ollama/ollama

ENV OLLAMA_HOST "0.0.0.0"

RUN apt install curl -y

# ollama pull deepseek-coder
RUN ollama serve & sleep 10 && echo "Pulling model..." && ollama pull orca-mini 

COPY entrypoint.sh /entrypoint.sh
# Make the script executable
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]