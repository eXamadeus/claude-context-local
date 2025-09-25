# Claude-Context Local

This is a repo that holds a `docker-compose.yml` to run [claude-context](https://github.com/zilliztech/claude-context) locally.

Requirements:
 - [Ollama](https://ollama.com/download)
 - [Docker](https://www.docker.com/)

Once you have those installed and running, you can start the containers:

```bash
docker compose up -d
```

then add the MCP server to you claude code settings:

```bash
claude mcp add claude-context \
  --env EMBEDDING_PROVIDER=Ollama \
  --env OLLAMA_HOST=http://127.0.0.1:11434 \
  --env OLLAMA_MODEL=nomic-embed-text \
  --env MILVUS_ADDRESS=127.0.0.1:19530 \
  -- npx @zilliz/claude-context-mcp@latest
```

Once that's done, you should have access to the MCP server in Claude Code!
