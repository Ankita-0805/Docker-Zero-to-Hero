FROM ubuntu:20.04

# Update package list and install Python, pip, and virtual environment tools
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv

# Set working directory
WORKDIR /app

# Copy requirements file
COPY requirements.txt .

# Create and activate a virtual environment, then install dependencies
RUN python3 -m venv venv && \
    . venv/bin/activate && \
    pip install --upgrade pip && \
    pip install -r requirements.txt

# Copy the rest of the application code
COPY . .

# Expose the application port
EXPOSE 8000

# Command to run the application within the virtual environment
CMD ["/bin/bash", "-c", "source venv/bin/activate && exec python your_script.py"]
