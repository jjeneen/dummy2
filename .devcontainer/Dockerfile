FROM mcr.microsoft.com/devcontainers/universal:2-linux

# Install xz-utils, Django, and MongoDB client tools
RUN apt-get update && \
    apt-get install -y xz-utils \
                       gnupg \
                       wget && \
    # Install MongoDB public GPG key
    wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | apt-key add - && \
    # Add MongoDB repository
    echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu focal 10gen" | tee /etc/apt/sources.list.d/mongodb-org-6.0.list && \
    # Install MongoDB client
    apt-get update && \
    apt-get install -y mongodb-org-tools && \
    # Install Django
    pip install django