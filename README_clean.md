
# Local Multimodal AI Chat

## Overview
Local Multimodal AI Chat is a powerful chat application that brings together different AI models to handle audio, images, and PDFs in one place. With Whisper AI for audio, LLaVA for image management, and Chroma DB for PDFs, this application offers a comprehensive solution for working with various data formats.

It also supports local model processing through the Ollama server and offers additional capabilities via integration with the OpenAI API, creating a versatile AI platform.

## Features
- Local Model Processing: Run models locally with Ollama, offering more control and privacy.
- OpenAI API Integration: Access a wide range of models for broader capabilities.
- Audio Chat with Whisper AI: Enables transcription and voice interactions.
- PDF Handling with Chroma DB: Engage with PDF files locally for insights and summaries.
- Image Understanding with LLaVA: Process and understand images intelligently.

## Quick Setup Using Docker Compose (Preferred Method)

1. Set the model save path by editing line 21 in the `docker-compose.yml` file.
2. Start the application by running this command in your terminal:
   
   docker compose up

3. If you don’t have a GPU, remove the `deploy` section from the `docker-compose.yml` file.
4. You can modify the `config.yaml` to suit your requirements.
5. Customize icons by placing your `user_image.png` and `bot_image.png` inside the `chat_icons` folder.
6. Open the app in your browser at: `0.0.0.0:8501`.

## Pulling Models

- Go to the Ollama library (https://ollama.com/library) and choose models.
- Pull a model by typing `/pull MODEL_NAME` in the chat bar.
- You will need at least:
  - An embedding model like `nomic-embed-text` for embedding PDF files.
  - A model that understands images, such as `llava`.

## Optional Configuration

- Modify `config.yaml` for further customization.
- Replace default images in the `chat_icons` folder with your own images.

## Recommendations for Windows Users

- If you are using the Ollama Docker container on Windows, the loading time for models can be slow. To avoid this, install the Ollama Desktop locally.
- Modify the `docker-compose.yml` file as follows:
  - Remove the existing `docker-compose.yml` file.
  - Rename `docker-compose_without_ollama.yml` to `docker-compose.yml`.
- Update the `config.yaml` file:
  - Use the Ollama Base URL by updating line 4 and removing line 3.

## Complete Manual Installation

1. Install Ollama by following their installation guide.
2. Create a Python virtual environment and activate it:

   python -m venv env
   source env/bin/activate

3. Upgrade pip and install the required dependencies:

   pip install --upgrade pip
   pip install -r requirements.txt

4. Install PyTorch for CPU:

   pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu

5. Initialize the database by running:

   python3 database_operations.py

6. Start the app:

   streamlit run app.py

7. Pull the models from Ollama as mentioned above.

## Contributions

We encourage contributions! Whether you’re adding new features, optimizing the code, or fixing bugs, all help is welcome. This project is designed to grow with community collaboration.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.
