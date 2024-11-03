# Use a lightweight Python base image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Install system dependencies for psycopg2 and other potential packages
RUN apt update -y && apt install -y libpq-dev gcc

# Copy the requirements file and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code into the container
COPY . .

# Expose the port your app runs on (if Flask uses a specific port, such as 5000)
EXPOSE 5000

# Define the command to run the application
CMD ["python", "app.py"]
