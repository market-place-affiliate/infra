# infra

Infrastructure setup for marketplace application with PostgreSQL and Redis.

## Services

This Docker Compose setup includes:

- **PostgreSQL (latest)**: Primary database
  - Port: 5432
  - Default database: marketplace
  - Default user: postgres
  - Default password: postgres

- **Redis (latest)**: In-memory data store and cache
  - Port: 6379
  - Persistence enabled (AOF)

## Prerequisites

- Docker
- Docker Compose

## Usage

### Start all services

```bash
docker-compose up -d
```

### Stop all services

```bash
docker-compose down
```

### Stop and remove volumes

```bash
docker-compose down -v
```

### View logs

```bash
# All services
docker-compose logs -f

# Specific service
docker-compose logs -f postgresql
docker-compose logs -f redis
```

### Check service health

```bash
docker-compose ps
```

## Connection Details

### PostgreSQL

- **Host**: localhost
- **Port**: 5432
- **Database**: marketplace
- **Username**: postgres
- **Password**: postgres

Connection string: `postgresql://postgres:postgres@localhost:5432/marketplace`

### Redis

- **Host**: localhost
- **Port**: 6379

Connection string: `redis://localhost:6379`

## Data Persistence

Data is persisted in Docker volumes:
- `postgresql_data`: PostgreSQL data
- `redis_data`: Redis data

These volumes will persist even after containers are stopped.