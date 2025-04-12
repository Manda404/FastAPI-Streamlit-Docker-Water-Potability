# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory inside the container to /app
WORKDIR /app

# Copy the requirements file into the container at /app/requirements.txt
# This allows Docker to cache the dependencies layer for faster builds
COPY requirements.txt /app/requirements.txt

# Install Python dependencies from requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire current directory into the container's /app folder
COPY . /app

# Expose the port Streamlit will run on (default is 8501)
EXPOSE 8501

# Set the default command to run Streamlit with debug logging enabled
CMD ["streamlit", "run", "app.py", "--logger.level=debug"]