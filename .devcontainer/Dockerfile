FROM python:3.12-slim
RUN apt-get update && apt-get install -y \
    curl \
    git \
    git-lfs \
    && rm -rf /var/lib/apt/lists/*
RUN git lfs install --system 
RUN curl -LsSf https://astral.sh/uv/install.sh | sh

ENV PATH="/root/.local/bin:$PATH"
WORKDIR /app
//Cambiar 
RUN uv venv .venv

COPY requirements.txt .
//Cambiar 
RUN uv pip install --python .venv/bin/python -r requirements.txt

ENV VIRTUAL_ENV=/app/.venv
ENV PATH="/app/.venv/bin:$PATH"