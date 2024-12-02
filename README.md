
# Retrieval-Augmented Generation (RAG) Web App

This repository provides the Dockerized version of the "Secured Babak RAG App". Users can run the pre-built Docker image directly without rebuilding it.

## Features

- **Pre-built Docker Image**: No need to build the image; simply pull it from Docker Hub.
- **File Upload**: Supports files like `.txt`, `.pdf`, `.docx` for asking questions based on the content.
- **File Processing**: Processes uploaded files for efficient information retrieval.
- **Google Vertex AI Integration**: Answers are generated only from the uploaded documents.

## Prerequisites

1. **Docker**: Install Docker to run the app in a containerized environment.

## Setup and Usage

### 1. Pull the Docker Image

To use the app, pull the pre-built Docker image from Docker Hub:

```bash
docker pull babak02/secured-babak-rag-app:latest
```

### 2. Run the Docker Container

Run the Docker container with the following command:

```bash
docker run -p 8501:8501 babak02/secured-babak-rag-app:latest
```

This will start the app on your local machine.

### 3. Access the App

Once the container is running, open your browser and go to:

```plaintext
http://localhost:8501
```

### 4. Upload Files and Ask Questions

- **Upload Files**: Choose files (in `.txt`, `.pdf`, or `.docx` format).
- **Process Files**: The app will process the uploaded files.
- **Ask Questions**: Enter your question in the text field. The app will generate an answer based on the content of the uploaded documents.

## Example Usage

1. **Upload a `.pdf` file** with content about IoT devices.
2. **Ask** a question like, "What are the key features of IoT devices?" The app will respond using information from the uploaded file.

## Troubleshooting

- **Cannot Access App**: Ensure Docker is installed and the container is running.
- **Answer Not Found**: This occurs if the answer cannot be derived from the uploaded files.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Streamlit](https://streamlit.io/) for the user interface
- [Google Vertex AI](https://cloud.google.com/vertex-ai) for language model integration
- [FAISS](https://faiss.ai/) for fast vector search indexing

---

Happy coding!
