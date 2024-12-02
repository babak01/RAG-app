
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

Ensure you have the Google Cloud service account key file (.json format) that you downloaded in the previous step.

### On Unix-based Systems (Linux/macOS)

Run the Docker container using the following command, replacing `/path/to/your/service_account.json` with the actual path to your credentials file:

```bash
docker run -p 8501:8501     
   -e GOOGLE_APPLICATION_CREDENTIALS=/app/service_account.json     
   -v /path/to/your/service_account.json:/app/service_account.json     
   ghcr.io/babak01/secured-babak-rag-app:latest
```

### On Windows PowerShell

Use the following command with backticks (`) for line continuation:

```powershell
docker run -p 8501:8501 `
    -e GOOGLE_APPLICATION_CREDENTIALS=/app/service_account.json `
    -v C:\path	o\your\service_account.json:/app/service_account.json `
    ghcr.io/babak01/secured-babak-rag-app:latest
```

### Command Explanation:

- Exposes the Streamlit app on port `8501`.
- Sets the `GOOGLE_APPLICATION_CREDENTIALS` environment variable within the container.
- Mounts your service account JSON file into the container at `/app/service_account.json`.

Open your browser and go to `http://localhost:8501` to access the app.

## Uploading Files and Asking Questions

- **Upload Files**: Select files in `.txt`, `.pdf`, or `.docx` formats.
- **Process Files**: The app will process the uploaded content.
- **Ask Questions**: Input your question in the text field. The app will generate answers based on the uploaded documents.

## Repository Structure

- **README.md**: This documentation file.
- **LICENSE**: License information for the project.

*Note: The source code (`app.py`) is maintained privately.*

## License

This project contains code from Google LLC, originally licensed under the Apache License, Version 2.0. The modified version provided here also falls under the Apache License 2.0.

You may obtain a copy of the Apache 2.0 License at: [https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)

### Apache License 2.0 Notice:

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

For more information on licensing or usage, please see the LICENSE file included with this repository.

## Contact

For questions or feedback, please contact [babak01](https://github.com/babak01).

---


