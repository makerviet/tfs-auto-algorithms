from python:3.8.17-bullseye

RUN apt-get update && apt-get install ffmpeg libsm6 libxext6  -y

# Install dependencies
COPY requirements.txt /tmp/
RUN pip install --upgrade pip && \
    pip install -r /tmp/requirements.txt

# Copy source code
COPY . /workspace/auto_control

# Set working directory
WORKDIR /workspace/auto_control

# Set entrypoint
ENTRYPOINT ["python", "drive.py"]
