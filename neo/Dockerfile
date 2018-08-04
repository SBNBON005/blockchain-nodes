FROM ubuntu:17.10

RUN apt-get update && apt-get install -y \
    wget vim git-core libleveldb-dev sqlite3 libsqlite3-dev libunwind8-dev unzip python3.6

RUN wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb \
    && dpkg -i packages-microsoft-prod.deb

RUN apt-get update \
    && apt-get install -y dotnet-sdk-2.1.4 && \
    export PATH=$PATH:$HOME/dotnet && \
    dotnet --version

RUN wget https://github.com/neo-project/neo-cli/releases/download/v2.7.6.1/neo-cli-linux-x64.zip \
    && unzip neo-cli-linux-x64.zip

RUN cd neo-cli && dotnet neo-cli.dll --rpc --log

EXPOSE 20332
