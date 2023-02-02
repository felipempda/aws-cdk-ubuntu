FROM ubuntu:latest

# Install nodejs 18x + aws-cdk
RUN apt-get update && \ 
    apt-get install -y --no-install-recommends curl ca-certificates unzip jq && \
    curl -fsSL -o setup.sh https://deb.nodesource.com/setup_18.x && \ 
    bash ./setup.sh && \
    rm ./setup.sh && \  
    apt-get install -y nodejs --no-install-recommends && \
    npm install -g aws-cdk && \
    node -v && \
    npx aws-cdk --version && \
    apt-get clean

# Install AWS cli:
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    ./aws/install --bin-dir /usr/bin/ && \
    rm -rf awscliv2.zip ./aws/
