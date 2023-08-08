from nvcr.io/nvidia/pytorch:22.12-py3

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
