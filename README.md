# CENG413 Week 5 Lab: Docker Compose

The Week 4 service, now with a Redis container next to it. The two containers find each other **by name**.

| Endpoint | What it does |
|---|---|
| `/health` | `{"status": "ok"}` |
| `/greet?name=Ada` | greeting (word from `APP_GREETING`) |
| `/visit` | counter kept in Redis when `REDIS_HOST` is set, otherwise in a file |
| `/whoami` | hostname of the container that answered |

## Quick start

```bash
git pull
cd ceng413-hw2
docker compose up -d --build
docker compose ps                    # app and cache must both be Up
curl http://localhost:8000/visit
docker compose down -v