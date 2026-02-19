---
sidebar_position: 2
---

# Install and deploy

Use this guide when you want a working Superdesk instance.

If you only want a fast local demo, use [Quick Start](quick-start.md).

### Choose your setup

* **Local demo / evaluation**: [Quick Start](quick-start.md)
* **Development**: run backend + frontend separately
* **Production**: Docker Compose + reverse proxy (recommended)

### Prerequisites

#### Docker (local or production)

* Docker 20.10+
* Docker Compose 2.0+
* RAM: 4GB+ (local), 8GB+ (small production)
* Disk: 10GB+ (local), 50GB+ (production)

#### Development

* Backend: Python 3.8+, MongoDB 4.4+, Elasticsearch 7.x, Redis 6.x
* Frontend: Node.js 16+, npm 8+

### Install with Docker Compose (local)

This is the simplest “full stack on one machine” setup.

```bash
git clone https://github.com/superdesk/superdesk.git
cd superdesk

docker-compose -f docker-compose.yml up -d

docker-compose exec backend python manage.py app:initialize_data
docker-compose exec backend python manage.py users:create -u admin -p admin -e admin@example.com --admin
```

{% hint style="warning" %}
The `admin` / `admin` credentials often shown in examples are for **local testing only**. Use a strong password for any shared or production environment.
{% endhint %}

Open the UI at `http://localhost:9000`.

### Development install (backend + frontend)

#### 1) Backend (superdesk-core)

```bash
git clone https://github.com/superdesk/superdesk-core.git
cd superdesk-core

python3 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

pip install -r requirements.txt

cp settings_sample.py settings.py
# Edit settings.py for Mongo/ES/Redis

python manage.py app:initialize_data
python manage.py users:create -u admin -p admin -e admin@example.com --admin

python manage.py app:run
```

#### 2) Frontend (superdesk-client-core)

```bash
git clone https://github.com/superdesk/superdesk-client-core.git
cd superdesk-client-core

npm install
npm start
```

#### 3) Planning module (optional)

```bash
git clone https://github.com/superdesk/superdesk-planning.git
cd superdesk-planning
```

### Production deployment (Docker Compose)

#### Hardware

Minimum:

* 4 CPU cores
* 8GB RAM
* 50GB storage

Recommended:

* 8+ CPU cores
* 16GB+ RAM
* 200GB+ SSD storage

#### Start services

```bash
git clone https://github.com/superdesk/superdesk.git
cd superdesk

cp .env.example .env
# Edit .env

docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d

docker-compose exec backend python manage.py app:initialize_data
docker-compose exec backend python manage.py users:create -u admin -p admin -e admin@example.com --admin
```

#### Reverse proxy (Nginx)

{% code title="nginx.conf" %}
```nginx
server {
    listen 80;
    server_name superdesk.example.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name superdesk.example.com;

    ssl_certificate /etc/ssl/certs/superdesk.crt;
    ssl_certificate_key /etc/ssl/private/superdesk.key;

    location / {
        proxy_pass http://frontend:9000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }

    location /api {
        proxy_pass http://backend:5000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;

        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }

    location /api/upload {
        proxy_pass http://backend:5000;
        client_max_body_size 500M;
    }
}
```
{% endcode %}

### Verification

* UI loads and you can log in.
* Backend responds:

```bash
curl http://localhost:5000/api/
```

### Operations

#### Backups

```bash
mongodump --uri="mongodb://localhost/superdesk" --out=/backup/mongo
```

#### Migrations

```bash
docker-compose exec backend python manage.py db:upgrade
```

### Next steps

* For architecture and extensions, go to the [Developer Guide](../developer-guide/index.md).
* For planning, see [Superdesk Planning](../developer-guide/planning/index.md).
