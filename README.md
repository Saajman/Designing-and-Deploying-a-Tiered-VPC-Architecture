# Designing-and-Deploying-a-Tiered-VPC-Architecture

---

## 📌 Project 1: Designing and Deploying a Tiered VPC Architecture

### 🎯 Objective
Design and implement a secure, highly available, and fault-tolerant VPC by provisioning public and private subnets across multiple availability zones, integrating internet and NAT gateways, and enforcing traffic control through security groups and NACLs.

### 🛠 Steps
1. **VPC Creation** – Created a new VPC with CIDR block `10.0.0.0/16`.
2. **Subnets** – Two public and two private subnets across different Availability Zones.
3. **Internet Gateway** – Attached for public internet access.
4. **Route Tables** – Separate tables for public/private subnets and associations.
5. **NAT Gateway** – Deployed in a public subnet for private subnet outbound internet access.
6. **Security Groups** – Configured for SSH, HTTP, and Load Balancer access.

### 💡 Recommendation
- Use **AWS CloudFormation/Terraform** for Infrastructure as Code.
- Enable **AWS CloudTrail, Config, and GuardDuty** for governance and threat detection.
- Consider **AWS Transit Gateway** and **Service Control Policies** for centralized governance.

### ✅ Conclusion
Successfully deployed a **tiered VPC** that balances security, scalability, and availability across multiple Availability Zones. This provides a strong foundation for secure cloud applications.

---

## 📌 Project 2: Auto-Scaling and Load Balancing Implementation

### 🎯 Objective
Implement **Auto Scaling Groups (ASG)** and **Application Load Balancer (ALB)** to ensure high availability and handle fluctuating loads.

### 🛠 Architecture
- **ALB** receives HTTP/HTTPS traffic and routes it across multiple AZs.
- **ASG** dynamically scales EC2 instances based on demand.
- **Launch Template + AMI** ensures consistency in instance creation.
- **Monitoring** via CloudWatch Alarms and ALB Health Checks.

### 🛠 Steps
1. Launched EC2 instances and installed Apache web server.
2. Created **Target Group** and configured **ALB health checks**.
3. Created **Application Load Balancer** to distribute traffic.
4. Configured **ASG** with scaling policies (CPU > 50%).
5. Tested scaling using **stress tool**.

### 💡 Recommendation
- Enable **HTTPS (ACM Certificates)** on ALB.
- Use **Auto Scaling lifecycle hooks** for better control.
- Add **Amazon EFS/S3** for shared storage.
- Enable **AWS Systems Manager** for secure instance management.
- Deploy **AWS WAF** for protection against web threats.

### ✅ Conclusion
The system delivers a **highly available and fault-tolerant architecture** with efficient traffic distribution and dynamic scaling. This ensures performance optimization and cost efficiency.

---

## 📌 Project 3: Student Grade Management System (AWS EC2, DynamoDB & Python)

### 🎯 Objective
- Implement monitoring and logging solutions.
- Interact with **AWS DynamoDB** using Python & Boto3.
- Apply **IAM roles** for secure service-to-service communication.
- Gain hands-on Python scripting experience.

### 🛠 Architecture
- **EC2 Instance** with Python & Boto3 environment.
- **IAM Role** with DynamoDB full access attached to EC2.
- **Python Script** (`student_logger.py`) to log student data.
- Data stored in **DynamoDB Students Table**.

### 🛠 Steps
1. Created **DynamoDB Table** – `Students` with `StudentID` as partition key.
2. Created and attached **IAM Role** with DynamoDBFullAccess to EC2.
3. Installed **Python3 + Boto3** on EC2.
4. Wrote **student_logger.py** script for inserting student data.
5. Verified database entries via DynamoDB console.

### 💡 Recommendation
- Integrate **AWS CloudWatch** for real-time monitoring.
- Use **AWS Systems Manager** for configuration management.

### ✅ Conclusion
Successfully built a **student grade management system** using EC2, DynamoDB, and Python. This project provided practical exposure to AWS services, IAM configuration, and Python scripting.

---

## 📌 Project Report: Infrastructure Configuration & Testing

### 🛠 Challenges & Resolutions
1. **NACL Restrictions** – Blocked access during stress testing → fixed by removing problematic entry.
2. **Database Naming Conflict** – Resolved by correcting misconfigured database name.
3. **Time & Energy Demands** – Required long troubleshooting sessions, enhancing problem-solving skills.

### ✅ Summary
This capstone project simulated **real-world infrastructure management** challenges and solutions. The team gained hands-on experience in networking, database management, and troubleshooting under pressure.

A big thank you to our trainers **Ajara Amadu and Esther Awudu** for their mentorship and support.

---

## 📂 Repository Structure (Suggested)
```
capstone-cloud-projects-group5/
├── README.md        # Main documentation (this file)
├── Project1_VPC.md  # Detailed VPC notes (optional)
├── Project2_ASG.md  # Detailed Auto Scaling notes (optional)
├── Project3_StudentLogger.md # Detailed DynamoDB project notes (optional)
├── src/
│   └── student_logger.py
├── diagrams/
│   ├── vpc-architecture.png
│   ├── auto-scaling-architecture.png
│   └── student-logger-architecture.png
└── GROUP5_Presentation.pdf  # Original slides
```

---

## 🚀 Next Steps
- Upload to GitHub repository.
- Add diagrams/screenshots to `diagrams/` folder.
- Include `student_logger.py` script in `src/` folder.

---

## 🙏 Acknowledgments
This project reflects **team collaboration, problem-solving, and cloud engineering skills** developed throughout our AWS training program.
