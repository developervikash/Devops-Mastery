
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

Sure Vikash, here’s a simple, clear explanation without too many emojis or technical jargon — just plain, human-style:

---

### 1. `docker run -it ubuntu`

This command starts a new Ubuntu container and opens an interactive terminal. It means you can directly enter commands inside that Ubuntu environment, like you're using a fresh Linux system. Useful when you want to explore or test things inside Ubuntu.

---

### 2. `docker run -itd ubuntu`

This also starts an Ubuntu container with terminal access, but adds the `-d` flag which runs it in the background (detached mode). However, since Ubuntu doesn’t have any default program running in the background, it will start and stop immediately unless you tell it to keep doing something. So this command doesn’t do much unless you add more instructions.

---

### 3. `docker run -p 80:80 nginx`

This command runs an Nginx web server and maps port 80 of your computer to port 80 of the container. So if you open your browser and go to `http://localhost`, you will see the Nginx welcome page. It runs in the foreground, so your terminal will stay connected to it until you stop it.

---

### 4. `docker run -d -p 80:80 nginx`

This is the same as the previous one, but it adds `-d` to run the Nginx container in the background. It keeps your terminal free while the web server continues running. This is the preferred way to run a service like Nginx for real use.

---

### Note:

The command `docker run -d-p 80:80 nginx` is **wrong** because `-d` and `-p` need to be separate with a space. It should be: `docker run -d -p 80:80 nginx`.

---


