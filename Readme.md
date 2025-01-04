# Project Name

## Setup

### 1. Set Environment Variable
Ensure pipenv installs packages in the virtual environment of the current project. This forces the virtual environment to be created inside the project directory (in `.venv`).

```sh
export PIPENV_VENV_IN_PROJECT=1
```

### 3. Set the environment file .env variable with following keys

Modify the value for HF_TOKEN to reflect your Hugging Face token and replace value for PROJECT_PATH to reflect where you have cloned this project

```sh
HF_TOKEN=hf_XXXX
PROJECT_PATH=D:\gitprojects
```

### 3. Create Conda Environment

Create a Conda environment with Python 3.11.11

```sh
conda create --prefix ./.venv python=3.11.11
```

### 4. Install Packages

Install the required packages using pipenv.

```sh
pipenv install
```
