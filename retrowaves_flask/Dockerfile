FROM python:3.11

# Set the working directory inside the container
WORKDIR /app

# Copy project files to the container
COPY . /app

# Install dependencies
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

# Expose port 8000 for Flask/Gunicorn
EXPOSE 8000

# Start the application using Gunicorn
CMD ["gunicorn", "-b", "0.0.0.0:8000", "app:app"]
