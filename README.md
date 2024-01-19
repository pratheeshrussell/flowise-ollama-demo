# Flowise - demo setup
Flowise demo

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