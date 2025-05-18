# Use Microsoft VSCode devcontainers base Python image
ARG VARIANT=3.13
FROM mcr.microsoft.com/vscode/devcontainers/python:${VARIANT}

# Copy requirements.txt into the image
COPY requirements.txt /tmp/pip-tmp/

# Install dependencies
RUN python -m pip install --upgrade pip \
    && python -m pip install --no-cache-dir -r /tmp/pip-tmp/requirements.txt \
    && pip install pre-commit ruff

# Optionally: Install pre-commit hooks
# (You may want to install hooks in dev only, not global container. If you want to install in container build, use WORKDIR or specify the repo)
# RUN pre-commit install

# Set workdir (optional)
WORKDIR /workspaces/${REPO_NAME:-app}
