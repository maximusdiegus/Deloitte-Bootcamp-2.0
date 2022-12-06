# Use Python 3.6 or later as a base image
FROM python:3.6

# Copy contents into image
COPY requirements.txt .
COPY . .

# Install pip dependencies from requirements
RUN pip3 install -r requirements.txt

# Set YOUR_NAME environment variable
LABEL version="1.0"

# Expose the correct port
EXPOSE 8080

# Create an entrypoint
ENTRYPOINT [ "python", "app.py" ]

CMD python3 app.py
