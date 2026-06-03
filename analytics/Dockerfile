
FROM public.ecr.aws/docker/library/python:3.9-slim

WORKDIR /app

# Copy requirements first so dependency changes are visible during build
COPY requirements.txt /app/requirements.txt

# Show requirements during build and install dependencies
RUN cat /app/requirements.txt && pip install --no-cache-dir -r /app/requirements.txt

# Copy application source after dependencies
COPY . /app

EXPOSE 5153

CMD ["python", "app.py"]
