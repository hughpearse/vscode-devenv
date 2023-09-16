FROM ubuntu:jammy

# Install VSCode
RUN apt-get update -y \
    && apt-get install -y software-properties-common apt-transport-https wget \
    && wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg \
    && install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/ \
    && sh -c 'echo "deb [arch=amd64 signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list' \
    && rm -f packages.microsoft.gpg \
    && apt-get update -y \
    && apt-get install -y code openjdk-11-jdk git \
    && groupadd developer \
    && useradd -m -g developer developer

USER developer

CMD code tunnel
