# alt.hub
A simple CLI wrapper for Hugging Face Hub to enable more fine-grained control when downloading and uploading files.

## About
alt.hub is a Command Line Interface (CLI) tool designed as a wrapper for the popular Hugging Face Hub, providing users with additional options for managing 
their model files.

## System Requirements
This project has been tested on Python 3.10+ and should work well on most Unix-based systems like Linux or MacOS.

## Installation
To get started with alt.hub:

1. Clone the repository from the source URL:

```sh
# Clone the repository
git clone https://github.com/teleprint-me/alt.hub
```

2. Create a virtual environment and install dependencies without affecting your system's global packages using the following commands:

```sh
# Setup the virtual env
poetry shell
# Install dependencies only
poetry install --no-root
```

3. Authenticate with Hugging Face Hub by setting up API keys in an `.env` file as follows:

```sh
echo HUGGINGFACE_WRITE_API='hf_write_key' > .env
echo HUGGINGFACE_READ_API='hf_read_key' >> .env
```

## Usage
alt.hub provides a variety of commands for downloading, uploading, and managing files on Hugging Face Hub using the `python -m hf.cli.hub` command. Here are 
some examples:

- Download model weights from the Hugging Face Model Hub:

```sh
python -m hf.cli.hub download -e .env -i <repository_id>
```

Replace `<repository_id>` with the ID of your desired repository (e.g., mistralai/Codestral-22B-v0.1).

- Upload local model weights to your personal Hugging Face Model Hub space:

```sh
python -m hf.cli.hub upload -e .env -i <repository_id> -p <local_path>
```

Replace `<local_path>` with the path to the directory or file you'd like to upload, and replace `<repository_id>` as before.

### Options
- `-e .env`: Specifies the path to your environment variables file (`.env`) containing Hugging Face API keys.
- `-i <repository_id>`: The ID of the repository you're interacting with on Hugging Face Hub.
- `-p <local_path>`: The local path from which to download or upload files or directories.

## Contribution Guidelines
Contributions are welcome! Please follow common contribution guidelines before submitting any pull requests.

## License
alt.hub is licensed under the AGPL license. See [LICENSE](LICENSE) for more information.
