# Async DataFrame Processing with Docker

For experiment of ChatGPT canvas

This repository contains an example project for processing multiple pandas DataFrames asynchronously, utilizing MongoDB as the database backend. The setup is containerized using Docker and Docker Compose for easy deployment.

## Prerequisites

- Docker
- Docker Compose

## Getting Started

### Clone the Repository
```sh
git clone <repository_url>
cd <repository_directory>
```

### Setup

1. Make sure you have Docker and Docker Compose installed on your machine.
2. Create a `requirements.txt` file to include all the dependencies for the Python script. An example of required packages:
    ```
    pandas
    pymongo
    motor
    asyncio
    ```
3. Place your CSV files (`your_data1.csv`, `your_data2.csv`, etc.) in the root directory.

### Running the Application

To run the application, use Docker Compose:

```sh
docker-compose up --build
```

This command will:
- Build the Docker image for the Python application.
- Build the MongoDB container using the provided Dockerfile.
- Start the async processing application container.

The application will process the CSV files asynchronously and store the results in the MongoDB database.

### Environment Variables

- `MONGO_URI`: MongoDB connection URI. Defaults to `mongodb://root:example@mongodb:27017/`.
- `DB_NAME`: MongoDB database name. Defaults to `database_name`.

### Stopping the Application

To stop the application, use:

```sh
docker-compose down
```

### File Structure

- `Dockerfile`: Defines the image for the Python application.
- `Dockerfile.mongodb`: Defines the image for the MongoDB container.
- `docker-compose.yml`: Defines and configures services (MongoDB and the Python app).
- `async_dataframe_processing.py`: The main Python script to process the DataFrames.
- `README.md`: This file.

## License

This project is licensed under the MIT License.
