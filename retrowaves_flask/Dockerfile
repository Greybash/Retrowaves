# Use Python 3.11 as the base image
FROM python:3.11

# Install system dependencies (if needed for dlib or other packages)
RUN apt-get update && apt-get install -y \
    cmake \
    build-essential \
    libboost-all-dev \
    libopenblas-dev \
    liblapack-dev \
    libx11-dev \
    libatlas-base-dev \
    libjpeg-dev \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory inside the container
WORKDIR /app

# Copy project files
COPY . /app

# Upgrade pip and install Python dependencies
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

# Expose port 8000 for Flask/Gunicorn
EXPOSE 8000

# Start the application using Gunicorn
CMD ["gunicorn", "-b", "0.0.0.0:8000", "app:app"]
