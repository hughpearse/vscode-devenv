# Visual Studio Code on Docker
Ever noticed when you join a new job, they provide instructions for setting up the development environment? Why dont they dockerize it?

# Instructions

Setup Docker and Compose on your host:

```bash
user@laptop$ sudo yum update
user@laptop$ sudo yum install -y yum-utils
user@laptop$ sudo yum-config-manager --add-repo http://yum.oracle.com/public-yum-ol7.repo
user@laptop$ sudo yum-config-manager --enable *addons
user@laptop$ sudo yum update
user@laptop$ sudo yum install docker-engine
user@laptop$ sudo systemctl enable --now docker
user@laptop$ sudo groupadd docker
user@laptop$ sudo usermod -aG docker ${USER}
user@laptop$ sudo curl -L "https://github.com/docker/compose/releases/download/v2.20.2/docker-compose-linux-$(uname -m)" -o /usr/local/bin/docker-compose
user@laptop$ sudo chmod +x /usr/local/bin/docker-compose
user@laptop$ sudo systemctl reboot
```

Clone the reop

```bash
user@laptop$ git clone http://example.git
```

Build and run the container

```bash
user@laptop$ cd vscode-devenv
user@laptop$ docker-compose up vscode-fedora
```

Log in to the tunnel

```text
vscode-fedora  | * Visual Studio Code Server
vscode-fedora  | *
vscode-fedora  | * By using the software, you agree to
vscode-fedora  | * the Visual Studio Code Server License Terms (https://aka.ms/vscode-server-license) and
vscode-fedora  | * the Microsoft Privacy Statement (https://privacy.microsoft.com/en-US/privacystatement).
vscode-fedora  | *
vscode-fedora  | To grant access to the server, please log into https://github.com/login/device and use code ABCD-1234
```

Log into https://github.com/login/device and you're ready to code in your vscode tunnel https://vscode.dev/tunnel/1234abcdef1234
