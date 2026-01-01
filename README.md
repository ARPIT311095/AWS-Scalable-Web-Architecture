<h1> Please find the attached Images in architecture-diagram.png folder in present image the loadbalencer is working fine and ASG is also workig properlly </h1>

<h1> 🚀 Project Overview </h1>
This project demonstrates the deployment of a Highly Available and Fault-Tolerant web application using AWS core services. The architecture is designed to handle variable traffic loads automatically and ensure zero downtime through self-healing mechanisms.

<h1> 🏗️ Architecture </h1>
The infrastructure is built across multiple Availability Zones (AZs) to prevent a single point of failure.

Application Load Balancer (ALB): Distributes incoming HTTP traffic across multiple healthy EC2 instances.

Auto Scaling Group (ASG): Automatically maintains the desired instance count and scales out/in based on CPU utilization.

EC2 Instances: Web servers hosted on Amazon Linux, bootstrapped with Nginx.

Target Group: Monitors instance health on Port 80 to ensure traffic is only routed to functional nodes.


<h1> Project Structure </h1>

AWS-Scalable-Web-Architecture/
├── README.md                 # Project documentation
├── architecture-diagram.png  # Visual representation of the setup
├── images/                   # Screenshots of AWS Console (Healthy Targets, ALB URL)
└── scripts/
    └── user-data.sh          # Automation script for server setup
    

<h1>⚙️ Setup & Configuration</h1>

To ensure every new instance launched by the ASG is ready to serve traffic, I used the following bootstrap script:
#!/bin/bash
sudo yum update -y
sudo amazon-linux-extras install nginx1 -y
sudo systemctl start nginx
sudo systemctl enable nginx
    <h2>
    Note: This automation solves the "502 Bad Gateway" issue by ensuring the web server starts immediately upon instance launch.</h2>

<h1> Load Balancer & Health Checks</h1>
Configured a Target Group on Port 80.
Defined Health Checks to monitor the root path (/).
Attached the Target Group to an Application Load Balancer to provide a single DNS endpoint for users.    

<h1> 🧪 Testing & Validation </h1>
Load Balancing Verification: Confirmed that the Application Load Balancer (ALB) successfully distributes incoming traffic across all healthy registered targets. By refreshing the ALB DNS endpoint, I verified that requests are being routed to different instances, ensuring no single server is overloaded.

Auto Scaling (Scale-Out) Test: Simulated a high-traffic scenario by increasing the CPU utilization on the instances using the yes > /dev/null & command. The CloudWatch alarms successfully triggered a scale-out event, and the Auto Scaling Group (ASG) automatically launched new instances to handle the increased load.

High Availability & Self-Healing: Tested the infrastructure's resilience by manually terminating a running EC2 instance. The ASG immediately detected the "Unhealthy" state and provisioned a new instance to maintain the Desired Capacity. The application remained accessible via the ALB URL throughout this process, proving zero downtime.
