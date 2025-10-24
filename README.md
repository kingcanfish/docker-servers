# Docker Servers Project

This is a collection of servers based on Docker Compose, including multiple common services for quick deployment and operation of various tools and services.

## Project Structure

- **clash/**: Clash proxy service for network proxy and traffic splitting.
- **it-tools/**: IT tools collection, providing online tools like JSON formatting, Base64 encoding, etc.
- **nginx-proxy-manager/**: Nginx Proxy Manager for managing Nginx reverse proxy and SSL certificates.
- **postgres/**: PostgreSQL database service.
- **qbittorrent/**: qBittorrent download client.
- **qdrant/**: Qdrant vector database for AI and search applications.
- **samba/**: Samba file sharing service.
- **speedtest/**: Speedtest network speed testing tool.
- **valkey/**: Valkey cache database (Redis compatible).
- **windows/**: Windows-related services or containers (depending on configuration).

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

Ensure Docker and Docker Compose are properly installed and running.

## Installation and Startup

1. Clone or download this project to a local directory.

2. Navigate to the project root directory:
   ```
   cd /path/to/docker-servers
   ```

3. For services that require configuration (such as nginx-proxy-manager, postgres, qbittorrent, qdrant), check the corresponding `.env` file and modify environment variables as needed.

4. Start all services:
   ```
   docker-compose up -d
   ```
   This will start all defined services in the background.

5. Stop services:
   ```
   docker-compose down
   ```

## Service Access

Each service is accessible via the ports defined in its docker-compose.yaml file. Here are common services and default ports:

- **Nginx Proxy Manager**: http://localhost:81 (management interface)
- **IT Tools**: http://localhost:port (check it-tools/docker-compose.yaml)
- **PostgreSQL**: localhost:5432 (requires username/password configuration)
- **qBittorrent**: http://localhost:port (check qbittorrent/docker-compose.yaml)
- **Qdrant**: http://localhost:6333 (API)
- **Samba**: Network share (configured in samba/smb.conf)
- **Speedtest**: http://localhost:port (check speedtest/docker-compose.yaml)
- **Valkey**: localhost:6379
- **Clash**: Access proxy ports based on configuration

Please check each service's docker-compose.yaml file for exact ports and access information.

## Configuration

- Most services use `.env` files for configuration. Edit the respective `.env` file before starting.
- For Samba, the configuration file is at `samba/smb.conf`.

## Troubleshooting

- Ensure all ports are not occupied by other services.
- Check Docker logs: `docker-compose logs <service-name>`
- If a service fails to start, verify that environment variables in `.env` files are correct.
- For network-related issues, ensure the firewall allows necessary ports.

## Contributing

Feel free to submit Issues and Pull Requests to improve this project.

## License

This project uses the MIT License. See the [LICENSE](LICENSE) file for details.
