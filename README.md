#### ml-environment

---

docker-compose config for ML tasks:

* Jupyter Notebook + PyTorch + LLM libs (`pydantic.ai`, `langchain`, `openai`);
* MLflow (experiment tracking) + S3 (Minio) + PostgreSQL;
* llama-cpp server.

---

##### Launch without LLM server:

```bash
docker compose --env-file local.env up --build -d
```

```bash
docker compose --env-file local.env down -v
```

##### Launch with LLM server:

(drop LLM model to `models` dir and update `.env` file)

```bash
docker compose --env-file local.env --profile llm up --build -d
```

```bash
docker compose --env-file local.env --profile llm down -v
```
