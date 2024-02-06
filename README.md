# ShortifyMe - URL Shortening Service

This project is a URL shortening service implemented using Go Fiber and Redis. It allows users to shorten long URLs into shorter, more manageable links. Additionally, it provides a resolution mechanism to redirect short URLs back to their original long URLs.

## Features

- Shorten long URLs into custom or automatically generated short URLs.
- Set expiration times for short URLs.
- Rate limiting to prevent abuse of the API.
- Redirect short URLs back to their original long URLs.

## Prerequisites

Before running the project, ensure you have the following dependencies installed:

- Go (Golang)
- Docker
- Docker Compose

## Getting Started

To run the project locally, follow these steps:

1. Clone this repository to your local machine:

   ```bash
   git clone <repository_url>


2. Navigate to the project directory:

   ```bash
   cd <project_directory>

3. Create a .env file in the project root and define the following environment variables:

   ```bash
   DB_ADDR=db:6379
   DB_PASS=
   APP_PORT=:3000
   API_QUOTA=10
   DOMAIN=<your_domain>

Replace <your_domain> with your desired domain name.


4. Build and start the Docker containers using Docker Compose:

   ```bash
   docker-compose up -d

Once the containers are running, you can access the API at http://localhost:3000.


## API Endpoints
POST /api/v1: Shortens a long URL. Accepts a JSON payload with the following fields:

url: The long URL to shorten.
short: (Optional) Custom short URL. If not provided, a random short URL will be generated.
expiry: (Optional) Expiration time for the short URL in hours.
GET /<short_url>: Redirects a short URL to its original long URL.

## Sending Alerts
To send alerts in case of errors or rate limit exceeded, you can integrate a notification service like email or SMS. You can add error handling logic in the code to trigger alerts and use a third-party service to send notifications.
