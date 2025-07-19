====================== Deploying small application on Docker Container ================
1. Create your Python application (e.g., app.py)
# app.py
print("Hello from Docker!")

2. Create a requirements.txt file (if your app has dependencies)
If your application needs external libraries, list them in a requirements.txt file in the same directory as your Python script. For example, to install Flask for a web application: 
bash
flask # Example dependency

3. Create a Dockerfile
A Dockerfile contains instructions for building the Docker image that encapsulates your application and its dependencies. 
dockerfile
# Dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["python", "app.py"]


4. Build the Docker image
In the directory containing your app.py, requirements.txt, and Dockerfile, run the following command to build the Docker docker build -t my-python-app .
This command builds the image and tags it with the name my-python-app. 

5. Run the Docker container
docker run my-python-app
This will run the container and execute the CMD instruction from your Dockerfile, which in this case is python app.py, printing "Hello from Docker!" to your terminal. 

6. Accessing a web application (if applicable)
If your Python application is a web application (like a Flask app), you need to map a port from the container to your host machine when running the container. For example, if your Flask app runs on port 5000 inside the container: 
bash
docker run -p 5000:5000 my-python-app
Then, you can access your application in a web browser at http://localhost:5000/. 



=================== Vocabulary ============================

# Docker 
Is a tool that makes creating, deploying, and running applications easier with the use of containers.

# Docker containers 
that run on Docker Engine

#  Docker Engine
open-source container runtime called Docker Engine. 
Provides the runtime environment for containerized applications, enabling them to be built, shipped, and run consistently across different environments. 

# Docker Hub - 
1) Is a cloud-based public registry for Docker images.
2) Provides a web interface for browsing, searching, and managing your images. 
3) Integrates with CI/CD pipelines for automated image creation and deployment. 

# Docker registry
1) Is a storage and distribution system for Docker images, which can be public or private.
