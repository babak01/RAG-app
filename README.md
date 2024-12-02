
# Retrieval-Augmented Generation (RAG) Web App

This repository provides a Dockerized version of the "Secured Babak RAG App," enabling users to run the pre-built Docker image directly without the need for rebuilding.

## Features

- **Pre-built Docker Image**: Easily pull the image from GitHub Container Registry (GHCR) without building it yourself.
- **File Upload**: Supports `.txt`, `.pdf`, and `.docx` files for content-based querying.
- **File Processing**: Efficiently processes uploaded files for information retrieval.
- **Google Vertex AI Integration**: Generates answers solely from the uploaded documents.

## Prerequisites

1. **Docker**: Install Docker to run the app in a containerized environment.
2. **Google Cloud Account**: Obtain a service account with access to Vertex AI.
3. **Service Account Key**: Download the JSON key file for authentication.

## Setting Up Google Cloud and Enabling Vertex AI API

1. **Create a Google Cloud Project**:
   - Navigate to the [Google Cloud Console](https://console.cloud.google.com/).
   - Click on the project dropdown and select "New Project."
   - Enter a project name and click "Create."

2. **Enable Vertex AI API**:
   - Within your project, go to "APIs & Services" > "Library."
   - Search for "Vertex AI" and click on it.
   - Click "Enable" to activate the API.

3. **Create a Service Account**:
   - Go to "IAM & Admin" > "Service Accounts."
   - Click "Create Service Account."
   - Provide a name and description, then click "Create and Continue."
   - Assign the "Vertex AI User" role.
   - Click "Done."

4. **Generate a Service Account Key**:
   - In the service account list, select your newly created account.
   - Navigate to the "Keys" tab.
   - Click "Add Key" > "Create New Key."
   - Choose "JSON" and click "Create" to download the key file.

## Running the App

1. **Pull the Docker Image**:

   Replace `<YOUR_GITHUB_USERNAME>` with your GitHub username:

   ```bash
   docker pull ghcr.io/<YOUR_GITHUB_USERNAME>/secured-babak-rag-app:latest
   ```

2. **Run the Docker Container**:

   Replace `/path/to/your/service_account.json` with the actual path to your service account key file:

   ```bash
   docker run -p 8501:8501        -e GOOGLE_APPLICATION_CREDENTIALS=/app/service_account.json        -v /path/to/your/service_account.json:/app/service_account.json        ghcr.io/<YOUR_GITHUB_USERNAME>/secured-babak-rag-app:latest
   ```

   This command maps the service account key into the container and sets the necessary environment variable for authentication.

3. **Access the App**:

   Once the container is running, open your browser and navigate to:

   ```plaintext
   http://localhost:8501
   ```

## Uploading Files and Asking Questions

- **Upload Files**: Select files in `.txt`, `.pdf`, or `.docx` formats.
- **Process Files**: The app will process the uploaded content.
- **Ask Questions**: Input your question in the text field. The app will generate answers based on the uploaded documents.

## Repository Structure

- **Dockerfile**: Instructions to build the Docker image.
- **README.md**: This documentation file.
- **LICENSE**: License information for the project.

*Note: The source code (`app.py`) is maintained privately.*

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or feedback, please contact [babak01](https://github.com/babak01).

---

Happy coding!
