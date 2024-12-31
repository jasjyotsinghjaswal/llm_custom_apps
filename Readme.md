# Project Name

## Setup

### 1. Set Environment Variable
Ensure pipenv installs packages in the virtual environment of the current project. This forces the virtual environment to be created inside the project directory (in `.venv`).

```sh
export PIPENV_VENV_IN_PROJECT=1
```

### 2. Create Conda Environment
Create a Conda environment with Python 3.11.11

```sh
conda create --prefix ./.venv python=3.11.11
```

### 3. Install Packages
Install the required packages using pipenv.
```sh
pipenv install
```