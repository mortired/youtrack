# YouTrack Docker Setup

This repository contains a Docker Compose configuration for running YouTrack, a project management and issue tracking tool by JetBrains.

## Prerequisites

- Docker
- Docker Compose

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
   YOUTRACK_HTTP_PORT=8080
   YOUTRACK_HTTPS_PORT=8443
   ```

3. **Start YouTrack:**
   ```bash
   docker-compose up -d
   ```

4. **Access YouTrack:**
   - HTTP: `http://localhost:8080`
   - HTTPS: `https://localhost:8443`

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

YouTrack runs on version `2025.2.94372` with automatic restart enabled. Modify the `.env` file to change ports, domain, or base URL as needed.
