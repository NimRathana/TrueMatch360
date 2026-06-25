
server {
    listen 80;
    server_name truematch.api.dev;

    location / {
        proxy_pass http://127.0.0.1:8001;  # FastAPI prod
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}

# ==========================
# Frontend ReactJS
# ==========================
server {
     listen 80;
    server_name truematch.dev;

    location / {
        proxy_pass http://127.0.0.1:3001;  # React prod
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
