FROM mcr.microsoft.com/devcontainers/go:1-1.23-bullseye
# Install the xz-utils package
RUN apt-get update

RUN curl -fsSL https://deb.nodesource.com/setup_lts.x | bash - && \
 apt-get install -y nodejs


RUN go install github.com/sqlc-dev/sqlc/cmd/sqlc@latest
RUN go install github.com/air-verse/air@v1.60.0
RUN chmod -R 777 /go
RUN npm install -g dbmate
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
RUN sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
RUN sudo apt update
RUN sudo apt install -y postgresql-client-14
