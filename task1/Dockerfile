# Use the latest Ubuntu image as the base
FROM ubuntu:latest

# Update APT and upgrade installed packages
RUN apt-get update && apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Remove EXTERNALLY-MANAGED error if present
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Set the working directory to /app
WORKDIR /app

# Copy the Flask application file to the Docker image
COPY ./api.py /app/api.py

# Expose port 5252 for the Flask server
EXPOSE 5252

# Run the Flask application
CMD ["python3", "api.py"]
