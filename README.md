In this Kubernetes practice, I completed the containerization and deployment of a Node.js application from scratch. First, I organized the code and dependencies in the project, wrote a Dockerfile to build the image, and successfully pushed the image to the Docker Hub personal repository. Then, I wrote the deployment file and service file for Kubernetes and deployed them locally through the Kubernetes cluster provided by Docker Desktop. After the initial deployment, although the Pod status showed normal operation, I encountered a connection failure when accessing the service. By checking the Pod log, I found that the actual listening port of the application was 5000, while I configured 3000 in the deployment file, causing the service to fail to connect correctly to the container. To solve this problem, I changed the container port in the deployment file and the target port in the service file to 5000 and reapplied the configuration. At the same time, I also found that the LoadBalancer type service in Docker Desktop does not automatically expose the public network port like the cloud platform, so I changed the service type to NodePort and specified a fixed port for access. Finally, I successfully accessed the Node.js application deployed in the Kubernetes cluster through a local browser, verifying the correctness of the entire deployment process. During this process, I gained an in-depth understanding of key knowledge points such as image building, service exposure, port mapping, and Pod log debugging, and also improved my ability to discover and solve problems in the actual environment.