# Highly Available & Fault-Tolerant Web Application on AWS

## 📌 Project Overview
This project demonstrates the deployment of a **Highly Available and Fault-Tolerant web application** using **AWS core services**.  
The architecture is designed to automatically handle **variable traffic loads**, provide **zero downtime**, and ensure **high availability** through AWS-managed self-healing mechanisms.

---

## 🏗️ Architecture Overview
The application follows a multi-tier architecture and leverages the following AWS services:

- **Amazon VPC** – Isolated network environment
- **Public & Private Subnets** – Secure traffic segregation
- **Application Load Balancer (ALB)** – Distributes incoming traffic across instances
- **Auto Scaling Group (ASG)** – Automatically scales EC2 instances based on demand
- **Amazon EC2** – Hosts the web application
- **Target Groups** – Health checks and traffic routing
- **Security Groups** – Controlled inbound and outbound access

---

## 🚀 Key Features
- High Availability across multiple Availability Zones
- Fault tolerance using Auto Scaling and health checks
- Automatic scaling based on traffic load
- Zero downtime during instance failure
- Secure architecture with private subnets
- Load-balanced traffic distribution

---

## 🔧 AWS Services Used
| Service | Purpose |
|-------|--------|
| EC2 | Compute resources for web application |
| ALB | Load balancing HTTP traffic |
| Auto Scaling | Automatic scaling and self-healing |
| VPC | Network isolation |
| Security Groups | Network-level security |
| IAM | Secure access and permissions |

---

## ⚙️ Deployment Steps (High Level)
1. Create a VPC with public and private subnets  
2. Launch EC2 instances in private subnets  
3. Configure Application Load Balancer in public subnets  
4. Create Target Group and register EC2 instances  
5. Configure Auto Scaling Group  
6. Deploy web application using User Data script  
7. Test application using Load Balancer DNS  

---

## 🧪 Testing & Validation
- Access application using **ALB DNS name**
- Stop an EC2 instance manually to verify self-healing
- Increase load to validate auto-scaling behavior
- Monitor health checks in Target Groups

---

## 📈 Benefits
- Improved reliability and uptime
- Automatic recovery from failures
- Cost optimization using dynamic scaling
- Production-ready AWS architecture

---

## 🧠 Learning Outcomes
- Understanding of AWS High Availability design
- Hands-on experience with Load Balancers and Auto Scaling
- Real-world fault-tolerant system implementation
- AWS networking and security best practices

---

## 📌 Use Cases
- Production web applications
- Enterprise-grade systems
- Scalable cloud-native applications

---

## 📄 Author
**Arpit Singh**  
AWS | DevOps | Cloud Infrastructure

---

## ✅ Conclusion
This project showcases a robust AWS architecture capable of handling real-world traffic demands while ensuring high availability, scalability, and fault tolerance.
