# A simple MERN stack application

## Create a network for the docker containers

```bash
docker network create demo
```

## Build the client

```bash
cd mern/frontend
docker build -t mern-frontend .
```

## Run the client

```bash
docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend
```

## Verify the client is running

Open your browser and type `http://localhost:5173`

## Run the mongodb container

```bash
docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongo:latest
```

## Build the server

```bash
cd mern/backend
docker build -t mern-backend .
```

## Run the server

```bash
docker run --name=backend --network=demo -d -p 5050:5050 mern-backend
```

## Using Docker Compose

```bash
docker compose up -d
```
