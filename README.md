# Bifrost — AI-gateway (Docker)

Нужен установленный Docker (macOS/Linux), запускается одной командой.

```sh
LITELLM_API_KEY=sk-... docker compose up -d
```

- UI: `http://localhost:8080`, админ `admin` / пароль из compose.yaml
  (дефолт `Change_Me_123!`, нужен только при первом запуске, дальше меняется в UI).
- Остановка: `docker compose down`. Логи: `docker compose logs -f`.
- `LITELLM_API_KEY` нужен при первом запуске — вшивается в БД. Забыли
  передать — удалите `data/` и запустите заново с ключом:
  `docker compose down && rm -rf data && LITELLM_API_KEY=sk-... docker compose up -d`.

На Linux задать адрес
Ollama строкой: `OLLAMA_URL=http://172.17.0.1:11434`. История логов
переносится вместе с `data/`.
