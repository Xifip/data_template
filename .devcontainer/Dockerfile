FROM python:3.11-slim

# Prevent interactive prompts
ENV DEBIAN_FRONTEND=noninteractive

# System dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential git curl && \
    rm -rf /var/lib/apt/lists/*

# Set workdir
WORKDIR /workspace

# Copy requirements early for caching
COPY requirements.txt /workspace/requirements.txt

RUN pip install --no-cache-dir -r requirements.txt

# Default command
CMD ["bash"]