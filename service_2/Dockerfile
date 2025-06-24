FROM python:3.13-slim

WORKDIR /app

# Install poetry
RUN pip install --no-cache-dir poetry

# Copy pyproject.toml and poetry.lock first for caching
COPY pyproject.toml poetry.lock* ./

# Disable venv creation and install dependencies
RUN poetry config virtualenvs.create false && poetry install --no-root

# Copy rest of the code
COPY . .

# Expose the Flask port
EXPOSE 8002

# Run the app
CMD ["python", "app.py"]
