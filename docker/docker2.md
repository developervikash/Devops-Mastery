 
✨ Write a Dockerfile
✨ Build a Docker image from it
✨ Run that image as a container
✨ Expose ports, install libraries, and even run Java apps inside a container
✨ Clean up unused stuff with docker system prune
✨ Configure EC2 security groups for access
It finally clicked for me how everything works together — and it’s honestly fun once you start practicing it hands-on.

🐳 DOCKER ADVANCE
🔹 Dockerfile → Image → Container
A Dockerfile is used to create a Docker image.
An image is then used to run a container.

🔹 Common Docker Terms
docker build → Builds an image from a Dockerfile.
docker run → Runs a container from an image.

📄 DOCKERFILE Structure:
Used to define what goes into the image. Think of it like a .java file in Java development.

Example:
# Base image (here: Alpine Linux with OpenJDK 17)
FROM openjdk:17-jdk-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy source code into container
COPY src/main.java /app/main.java

# Expose the port your app will run on
EXPOSE 8000

# Compile and run the Java file (example)
RUN javac main.java

# Command to run when the container starts
CMD ["java", "main"]

🛠 Notes:

Everything in the Dockerfile is to create a custom image.
If your application needs libraries, you should:
Install them via RUN commands.
Or copy them into the image.

🔧 Docker Commands:

 Build an Image:
docker build -t java-app:latest /src/dockerfile-directory

 List Images-
docker images

Run a Container:
docker run -d -p 8000:8000 java-app:latest

Security Group Setup (if using AWS EC2):

Go to Security Groups
Add Inbound Rule:
Type: Custom TCP
Port: 8000
Source: 0.0.0.0/0 (for open access)

🧹 Clean Up:
To remove stopped containers, dangling images, and free space:
docker system prune

🔄 Rebuilding After Code Change:
If you've made changes:

Rebuild the image:
docker build -t java-app:latest .

Stop the previous container:
docker ps   # Find container ID
docker stop <container_id>

Run the new one again:
docker run -d -p 8000:8000 java-app:latest

 

