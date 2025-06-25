# Use Python 3.11 slim image
FROM python:3.11-slim

# Set environment variables
ENV POETRY_VERSION=1.7.1 \
    POETRY_NO_INTERACTION=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

# Install system dependencies
RUN apt-get update && apt-get install -y curl build-essential && \
    curl -sSL https://install.python-poetry.org | python3 - && \
    ln -s /root/.local/bin/poetry /usr/local/bin/poetry && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Copy code
COPY . .

# Install dependencies with Poetry (no dev)
RUN poetry install --only main --no-root


# Expose port
EXPOSE 8002

# Run the app
CMD ["poetry", "run", "python", "app.py"]

