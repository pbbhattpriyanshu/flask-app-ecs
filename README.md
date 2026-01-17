# Flask App for ECS

A simple Flask web application designed to run on Amazon ECS (Elastic Container Service). This application demonstrates basic DevOps practices including containerization and deployment to AWS ECS.

## Features

- **Hello World Route** (`/`): Displays a welcome message.
- **Health Check** (`/health`): Returns server status for monitoring.
- **About Page** (`/about`): Provides information about the application.
- **Contact Page** (`/contact`): Shows contact details.

## Prerequisites

- Python 3.9 or higher
- Docker (for containerized deployment)
- AWS CLI (for ECS deployment)

## Local Development

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd flask-app-ecs
   ```

2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running Locally

Run the application:
```bash
python run.py
```

The app will be available at `http://localhost:80`.

## Docker

Two Dockerfile options are provided:

### Simple Dockerfile

Build and run with the basic Dockerfile:
```bash
docker build -t flask-app .
docker run -p 80:80 flask-app
```

### Multi-Stage Dockerfile

For a more optimized production image using distroless base:
```bash
docker build -f Dockerfile-multi -t flask-app-multi .
docker run -p 80:80 flask-app-multi
```

## Deployment to ECS

1. Build and push the Docker image to Amazon ECR.
2. Create an ECS cluster, task definition, and service.
3. Deploy the service to the cluster.

Detailed ECS deployment instructions can be found in the AWS documentation.

## Project Structure

- `app.py`: Main Flask application
- `run.py`: Entry point to run the app
- `requirements.txt`: Python dependencies
- `Dockerfile`: Simple Docker configuration
- `Dockerfile-multi`: Multi-stage Docker configuration for production
- `README.md`: This file

## Contributing

Feel free to submit issues and pull requests.

## License

This project is licensed under the MIT License.
