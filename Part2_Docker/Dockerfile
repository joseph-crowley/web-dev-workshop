# Use an official Python runtime as a base image
FROM python:3.9-slim

# Prevent Python from writing pyc files to disc
ENV PYTHONDONTWRITEBYTECODE 1
# Prevent Python from buffering stdout and stderr
ENV PYTHONUNBUFFERED 1

# Set the working directory in the container
WORKDIR /code

# Copy the current directory contents into the container at /code
COPY ./Part3_Django /code/

# Install pip with no cache to ensure no extra files are stored
RUN pip install --upgrade pip \
    && pip install --no-cache-dir -r requirements.txt

# Expose port 8000 to be accessible from the host
EXPOSE 8000

# CMD should be used to run the server, and it will be overridden by any command you put in docker-compose exec
# So it's commented out to highlight that it's not needed for the building phase
# CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
