🐳 DOCKER FUNDAMENTALS

⚙️ How Containers Work
* Containers do not consume pre-allocated resources like virtual machines.
* They use shared system resources (CPU, RAM, storage).
* If a container needs only 200MB of space, it will consume only 200MB, not more.
💡 Containerization is made possible through Docker.

🧠 Hypervisor vs Docker
* Hypervisor: Used in virtual machines (e.g., VirtualBox, VMware). It allocates separate OS and resources to each VM.
* Docker: Uses shared OS kernel (specifically Linux kernel) to run containers more efficiently with fewer resources.

🐧 Installing Docker (on Ubuntu)
sudo apt-get update
sudo apt-get install docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo systemctl status docker

🍏 Installing Docker (on macOS)
brew install --cask docker
docker --version

🔍 How Docker Works
Docker consists of the following components:
* Docker CLI → Command Line Interface
* Docker Daemon (dockerd) → Runs in the background and manages containers/images
* Containers → Lightweight isolated environments to run apps
* Docker Images → Blueprints used to create containers
Flow:
DOCKER CLI → Docker Daemon → Container

🧪 Common Docker Commands
* docker ps → Lists running containers
* cat /etc/group → Checks if you’re in the docker group
* If not in the group:
sudo usermod -aG docker $USER
newgrp docker  # Refresh group membership
🧠 $USER is an environment variable representing the currently logged-in user.

🚀 Docker File → Image → Container
* A Dockerfile is used to create a Docker image.
* An image is like a blueprint.
* A container is a running instance of that image.
Without a Dockerfile, you can directly pull and run prebuilt images using DockerHub.

🛠️ Example Docker Run Commands
docker run -it ubuntu      ,,,, Interactive terminal
docker run -itd ubuntu     ,,,, Interactive + detached (runs in background)
docker run -d -p 80:80 nginx   ,,,,, Run nginx in background and expose port 80
docker run -it -d -p 80:80 nginx …….Interactive + detached nginx

⛔ Stopping a Container
docker stop <container_id>

