# YouTrack Docker Setup

This repository contains a Docker Compose configuration for running YouTrack, a project management and issue tracking tool by JetBrains, with nginx-proxy and automatic SSL certificates via Let's Encrypt.

## Prerequisites

- Docker
- Docker Compose
- nginx-proxy network (external network named `nginx_proxy-tier`)

## Quick Start

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd youtrack
   ```

2. **Create environment file:**
   Create a `.env` file with the following variables:
   ```env
   YOUTRACK_DOMAIN=your-domain.com
   YOUTRACK_BASE_URL=https://your-domain.com
   LETSENCRYPT_EMAIL=your-email@example.com
   ```

3. **Start YouTrack:**
   ```bash
   docker-compose up -d
   ```

4. **Access YouTrack:**
   - HTTPS: `https://your-domain.com` (automatically secured with Let's Encrypt SSL)

## Management Commands

- **Stop services:**
  ```bash
  docker-compose down
  ```

- **View logs:**
  ```bash
  docker-compose logs -f youtrack
  ```

- **Restart services:**
  ```bash
  docker-compose restart
  ```

## Data Persistence

The following data is persisted in Docker volumes:
- `youtrack-data`: Application data
- `youtrack-conf`: Configuration files
- `youtrack-logs`: Log files
- `youtrack-backups`: Backup files

## Configuration

YouTrack runs on version `2025.2.94372` with automatic restart enabled. The setup includes:

- **nginx-proxy integration**: Automatic reverse proxy configuration
- **Let's Encrypt SSL**: Automatic SSL certificate generation and renewal
- **External network**: Uses `nginx_proxy-tier` network for proxy communication
- **Exposed port**: YouTrack runs on internal port 8080 (exposed to nginx-proxy)

Modify the `.env` file to change domain, base URL, or Let's Encrypt email as needed.
