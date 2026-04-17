# Node.js Docker Project

A sample Node.js application configured with Docker for easy deployment.

## Prerequisites

- Docker installed on your machine
- Docker Compose (optional, but recommended)

## Project Structure

```
nodejs-docker-project/
├── Dockerfile              # Docker image configuration
├── docker-compose.yml      # Docker Compose configuration
├── .dockerignore          # Files to exclude from Docker image
├── package.json           # Node.js dependencies
├── index.js              # Main application file
└── README.md             # This file
```

## Getting Started

### Method 1: Using Docker Compose (Recommended)

1. Build and start the container:
   ```bash
   docker-compose up --build
   ```

2. Access the application at `http://localhost:3000`

3. Stop the container:
   ```bash
   docker-compose down
   ```

### Method 2: Using Docker Commands

1. Build the Docker image:
   ```bash
   docker build -t nodejs-app .
   ```

2. Run the container:
   ```bash
   docker run -p 3000:3000 nodejs-app
   ```

3. Stop the container:
   ```bash
   docker stop <container_id>
   ```

## Available Endpoints

- `GET /` - Welcome message
- `GET /health` - Health check endpoint

## Development

To run in development mode with hot reload:

1. Install dependencies locally:
   ```bash
   npm install
   ```

2. Run with docker-compose (volumes are already configured):
   ```bash
   docker-compose up
   ```

## Customization

- Change the port in `docker-compose.yml` and `Dockerfile`
- Add environment variables in `docker-compose.yml`
- Modify `index.js` to add your application logic
- Update `package.json` with additional dependencies

## Troubleshooting

- If port 3000 is already in use, change it in `docker-compose.yml`
- Run `docker-compose down -v` to remove volumes if needed
- Use `docker logs <container_name>` to view logs
