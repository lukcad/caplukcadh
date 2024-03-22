ARG VARIANT="20"
FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:0-${VARIANT}

# install some useful tools
RUN apt-get update && apt-get -y install --no-install-recommends curl git sqlite3 

# Install SAP CAP SDK globally by using user node. 
# User `node` is created for 20 variant of miscosoft development docker
USER node
RUN npm install -g @sap/cds-dk
RUN npm install -g hana-cli
WORKDIR /home/node

# install public key and package for client to repository for Cloud Foundry
RUN wget -q -O - https://packages.cloudfoundry.org/debian/cli.cloudfoundry.org.key | sudo apt-key add -
RUN echo "deb https://packages.cloudfoundry.org/debian stable main" | sudo tee /etc/apt/sources.list.d/cloudfoundry-cli.list
RUN sudo apt-get update
RUN sudo apt-get install cf8-cli