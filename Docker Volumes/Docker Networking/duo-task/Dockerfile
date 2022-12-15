# Use Python 3.6 or later as a base image
FROM python:3.6
FROM nginx:1.23-alpine

# Copy contents into image
 COPY ./requirements.txt /app/requirements.txt

# Install pip dependencies from requirements
RUN pip install -r requirements.txt

# Set YOUR_NAME environment variable
ARG variable="Diego"
ENV YOUR_NAME=$variable

# Expose the correct port
EXPOSE 5000

# Create an entrypoint
ENTRYPOINT [ "python" ]

CMD ["app.py" ]

