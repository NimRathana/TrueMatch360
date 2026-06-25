
Installation

1. npm install
2. create .env in truematch360_web
3. create .env.dev
4. create docker-compose.dev.yml
5. run ( docker compose --env-file .env.dev -f docker-compose.dev.yml up -d --build)
6. stop ( docker compose --env-file .env.dev -f docker-compose.dev.yml down )
7. clear old image not use ( docker image prune )