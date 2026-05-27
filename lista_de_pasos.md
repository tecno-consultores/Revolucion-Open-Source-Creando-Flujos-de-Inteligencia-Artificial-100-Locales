# pasos para ejecutar cada componente

* Ejecutamos el siguiente comando para clonar el repositorio:

```bash
git clone https://github.com/tecno-consultores/llm-lab
```

* Ejecutamos docker pull para descargar todos los componentes:

```bash
docker compose -f docker-compose.yml --env-file env.example --profile n8n --profile n8n-worker --profile n8n-runner --profile qdrant --profile openwebui --profile ollama-gpu --profile searxng --profile opencode --profile hermes pull
```

* Antes de iniciar cualquier programa modificamos el archivo de variables:

```bash
nano env.example
```

* Ejecutamos ollama con el siguiente comando

```bash
docker compose -f docker-compose.yml --env-file env.example --profile ollama-gpu up -d
```

* Ahora, accedemos a ollama de la siguiente forma:

```bash
docker exec -it ollama bash
```

* Una vez dentro del contenedor debemos descargar los modelos que vamos a utilizar:

```bash
ollama pull qwen3.5:9b
```

```bash
ollama pull hermes3:8b
```

```bash
ollama pull nomic-embed-text-v2-moe
```

* Ahora si, ejecutamos nuestro primer modelo:

```bash
ollama run qwen3.5:9b
```
