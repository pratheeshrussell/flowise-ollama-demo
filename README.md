# Flowise - ollama demo setup
A Flowise-ollama demo

## Dockerfiles
### ollama
Modify the dockerfile in ollama folder. Currently pulling orca-mini during build time.  
  
NOTE that this will pull the orca-mini models during build time itself

### flowise
Image pulled directly from dockerhub.  The dockerfile in flowise folder is not used. You can use it if you need to make any customizations.

### Weaviate
Image pulled directly from dockerhub.  
comment it in docker-compose if not needed

## Start
```
docker compose up -d
```

UI will be available at http://localhost:4505/

## Port and host mapping
Only the port for flowise is accessible from outside the docker network. This is currently set to 4505.   

To access ollama from flowise container use the hostname **ollama** ie., *http://ollama:11434*   

similarly, the weaviate container can be accessed with hostname **weaviate**, example, *weaviate:8080*    

## Adding documents with data
Add your data to **custom_data** folder this will be mapped to **/var/custom_data** in flowise container. You can load it with **Folders with Files** document loader in flowise by specifying **/var/custom_data** or subfolders inside that

## Ollama Model files
The folder **ollama_models** is mapped to **/root/custom_models** in the ollama container. You can add your models and model files there however you would have to exec inside the container to load it into ollama for now.
```
sudo docker exec -it ollama /bin/bash
```
Read more about loading a model from modelfile [here](https://github.com/jmorganca/ollama/blob/main/docs/modelfile.md)
