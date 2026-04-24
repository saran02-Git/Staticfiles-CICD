Trend App – CI/CD Deployment using Jenkins, Docker, Terraform, and AWS EKS

Project Overview:
This project demonstrates a complete CI/CD pipeline to build, containerize, and deploy a React application to a Kubernetes cluster using Jenkins and AWS services.
The application source code was cloned from the provided GitHub repository and deployed in a production-ready environment.
The focus of this project is on infrastructure provisioning, CI/CD automation, containerization, Kubernetes deployment, and monitoring.

Architecture:
GitHub → Jenkins Pipeline → Docker Build → DockerHub → Amazon EKS → LoadBalancer → User

Source Code : GitHub
CI/CD : Jenkins Pipeline
Infrastructure Provisioning : Terraform
Build & Containerization : Docker
Container Registry : DockerHub
Orchestration : Amazon EKS (Kubernetes)
Deployment : Kubernetes Deployment & Service (LoadBalancer)
Monitoring : Grafana & Prometheus

Workflow:
1. Code is pushed to GitHub repository
2. GitHub webhook triggers Jenkins pipeline automatically
3. Jenkins pipeline:
   - Pulls latest source code from GitHub
   - Builds Docker image for the application
   - Tags and pushes image to DockerHub
4. Terraform provisions required AWS infrastructure such as VPC, IAM, EC2, and related resources
5. Kubernetes deployment:
   - Jenkins uses kubectl to apply deployment and service YAML files
   - Amazon EKS pulls the latest image from DockerHub
   - Application is deployed to the cluster
6. Service exposes the application through AWS LoadBalancer
7. Grafana & Prometheus is used to monitor application and cluster health.

Technologies Used:
AWS
Jenkins
Docker
Terraform
Amazon EKS
Kubernetes
DockerHub
GitHub
Grafana
Prometheus


Project Requirements Covered:
Dockerfile created to containerize the React application
Terraform main.tf used to provision infrastructure
DockerHub repository used to store container images
Kubernetes deployment and service YAML files created
Jenkins declarative pipeline configured for build, push, and deploy
GitHub webhook integrated with Jenkins for automatic builds
gitignore and dockerignore files added for proper version control
Open-source monitoring setup implemented for cluster or application health.

Deployment Files:
Dockerfile – Container image build instructions
main.tf – Terraform infrastructure configuration
deployment.yaml – Kubernetes Deployment configuration
service.yaml – Kubernetes Service configuration
Jenkinsfile – Declarative CI/CD pipeline definition
.gitignore – Files ignored by Git
.dockerignore – Files ignored during Docker build

Application Source:
Repository URL : https://github.com/Vennilavanguvi/Trend.git

Application Access:
The application is exposed through a Kubernetes LoadBalancer service running on Amazon EKS.
The deployed application runs on port 3000 as specified in the project requirements.
The application is served using Nginx configured to listen on port 3000, ensuring the container and service both expose the application correctly.

Application URL:
http://a4ca254fa7b8f42aa94f095dd9b4f6cf-2084988577.ap-south-1.elb.amazonaws.com:3000

Monitoring:
Grafana & Prometheus was used as an open-source monitoring solution to observe the health and performance of the application and cluster resources.
A lightweight monitoring setup was implemented to suit available infrastructure capacity while still providing useful visibility into deployment health.

Verification Commands:
kubectl get pods
kubectl get svc -o wide

The deployment verification confirms that the application is running in the Kubernetes cluster and exposed externally through a LoadBalancer service.

Challenges Faced:
This project involved troubleshooting across multiple DevOps and cloud infrastructure layers.

Key challenges included:
Jenkins installation and plugin configuration on EC2
Docker image build and push failures
Pod scheduling issues due to limited node capacity
Kubernetes metrics-server issues

Solutions Implemented:
Configured Jenkins with required plugins for Git, Docker, Kubernetes, and pipeline execution
Built and pushed Docker images successfully to DockerHub
Scaled or adjusted cluster resources to handle pod scheduling
Fixed metrics-server and monitoring configuration

Outcome
Fully functional CI/CD pipeline
Successful Docker image build and push
Infrastructure provisioned using Terraform
Kubernetes deployment automated through Jenkins
Application successfully deployed on Amazon EKS
Monitoring implemented using Grafana & Prometheus
Application accessible through LoadBalancer

Conclusion:
This project reflects hands-on experience in building and deploying a production-style CI/CD pipeline using Jenkins, Docker, Terraform, AWS, and Kubernetes. It highlights practical implementation of automation, infrastructure provisioning, containerization, orchestration, monitoring, and troubleshooting in a real-world DevOps workflow.
