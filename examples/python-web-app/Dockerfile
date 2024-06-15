FROM ubuntu

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

RUN apt-get update && \
    apt-get install -y python3-venv && \
    python3 -m venv venv && \
    . venv/bin/activate && \
    pip install --upgrade pip && \
    pip install -r requirements.txt && \
    cd devops

# # Install system dependencies and create a virtual environment
# RUN apt-get update && \
#     apt-get install -y python3-venv && \
#     python3 -m venv venv && \
#     . venv/bin/activate && \
#     pip install --upgrade pip && \
#     pip install -r requirements.txt
#       cd devops

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]