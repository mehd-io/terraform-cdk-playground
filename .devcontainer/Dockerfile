ARG VARIANT=3.8
FROM mcr.microsoft.com/vscode/devcontainers/python:${VARIANT}

ARG VERSION_TERRAFORM=0.13.0

# Nodejs
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - \
&& apt-get install -y nodejs

# Yarn
RUN curl -o- -L https://yarnpkg.com/install.sh | bash

# Terraform
RUN wget -q https://releases.hashicorp.com/terraform/${VERSION_TERRAFORM}/terraform_${VERSION_TERRAFORM}_linux_amd64.zip
RUN unzip terraform_${VERSION_TERRAFORM}_linux_amd64.zip
RUN install terraform /usr/local/bin
RUN terraform -v

# Terraform cdk
RUN npm install --global cdktf-cli

# Pipenv required for template cdk
RUN apt-get install -y pipenv