# simple-api

Minimal FastAPI service 

## Run locally

```bash
python -m venv .venv
source .venv/bin/activate 
pip install -r requirements.txt
uvicorn app.main:app --host 0.0.0.0 --port 8000
```

Open:
- http://localhost:8000/
- http://localhost:8000/docs

## Run with Docker

### Build + run

```bash
docker build -t simple-api:latest .
docker run --rm -p 8000:8000 simple-api:latest
```

### Docker Compose

```bash
docker compose up --build
```

## Endpoints

```bash
GET  /                 # HTML index
GET  /health           # health probe
GET  /jokes/list       # all jokes
GET  /jokes/random     # random joke
GET  /jokes/info       # env info (APP_ENV, DEBUG_MODE)
```

Example:

```bash
curl http://localhost:8000/jokes/random
```
