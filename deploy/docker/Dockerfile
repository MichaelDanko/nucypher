FROM python:3.7.0-slim-stretch

# Update
RUN apt update -y && apt upgrade -y
RUN apt install gcc libffi-dev wget -y

# Set the working directory to /app
WORKDIR /code

# Copy the current directory contents into the container at /app
COPY . /code
COPY get-alices-key /usr/local/bin/get-alices-key
RUN chmod +x /usr/local/bin/get-alices-key
# Run pipenv
RUN pip3 install .
RUN ./scripts/install_solc.sh

CMD ["/bin/bash"]
