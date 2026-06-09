Настройка Nginx
Nginx работает как единая точка входа. Он принимает все запросы и распределяет их между фронтендом и бэкендом.

Используемые порты:
Nginx слушает порт 80
Фронтенд работает на порту 5000
Бэкенд работает на порту 3000


В настройках Nginx прописаны два пути для проксирования:

server {
    listen 80;
    server_name 127.0.0.1;

    # Проксирование бэкенда (API)
    location /api/ {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }

    # Проксирование фронтенда (Интерфейс)
    location / {
        proxy_pass http://localhost:5000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}