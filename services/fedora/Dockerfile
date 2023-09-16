FROM fedora:40

# Install VSCode
RUN rpm --import https://packages.microsoft.com/keys/microsoft.asc \
    && sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo' \
    && yum install -y code git java-11-openjdk \
    && groupadd developer \
    && useradd -g developer developer

USER developer

CMD code tunnel
