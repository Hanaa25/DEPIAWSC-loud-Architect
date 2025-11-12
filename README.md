# Project 1: Building a Highly Available, Scalable Web Application

📄 The project documentation and architecture diagrams are included in **project1.pdf**.  

🖼️ All project screenshots and diagrams are contained within the **project1.pdf** file.  
![AWS Infrastructure](AWS Infrastructure Scalable-Web-App-ALB-AS.png)
## 🧩 Project Overview
The challenge is to **plan, design, build, and deploy** a web application on the **AWS Cloud** following the **AWS Well-Architected Framework** best practices.

During the **peak admissions period**, the application must support **thousands of users** and be:
- Highly available  
- Scalable  
- Load balanced  
- Secure  
- High performing  
- Cost optimized  

The application manages **student records** (view, add, delete, modify).

---

## 🎯 Requirements

### Functional
- The application must allow users to **view, add, delete, or modify** student records **without perceivable delay**.

### Load Balanced
- Traffic is **evenly distributed** to prevent resource overload or underutilization.

### Scalable
- The architecture must **scale automatically** based on user demand.

### Highly Available
- The solution must have **minimal downtime** even if a server becomes unavailable.

### Secure
- Database is **not directly accessible** from public networks.  
- Web servers and the database are accessible **only on appropriate ports**.  
- The web app is **accessible over the internet**.  
- **Database credentials** are stored securely (not hardcoded).

### Cost Optimized
- The design should **minimize operational costs**.

### High Performing
- Operations (view, add, delete, modify) must perform **without delay** under normal and peak loads.

---

## 🗂️ Project Phases

### Phase 1: Planning the Design and Estimating Cost

#### Task 1: Creating an Architectural Diagram
- Design a visual AWS architecture showing all components:
  - VPC, Subnets, EC2 Instances, Load Balancer, Auto Scaling, RDS, Secrets Manager.

#### Task 2: Developing a Cost Estimate
- Estimate 3-year cost with the following assumptions:
  - **EC2:** No upfront payment.  
  - **RDS:** Partial upfront payment.  
  - **Application Load Balancer:** Pay-as-you-go.

---

### Phase 2: Creating a Basic Functional Web Application

#### Task 1: Creating a Virtual Network
- Create a **VPC** named `project_app`.

#### Task 2: Creating a Virtual Machine
- Launch an **EC2 instance** named `web1`.

#### Task 3: Testing the Deployment
- Deploy the web app and verify access via browser.

---

### Phase 3: Decoupling the Application Components

#### Task 1: Creating and Configuring the Amazon RDS Database
- Create a database named `database1` in **Amazon RDS**.

#### Task 2: Configuring the Development Environment
- Update the web app code to connect to the RDS instance.

#### Task 3: Provisioning AWS Secrets Manager
- Create a secret named `Mydbsecret` to securely store DB credentials.

#### Task 4: Provisioning a Second Web Server
- Launch another **EC2 instance** named `web2`.

#### Task 5: Testing the Application
- Verify both web servers can connect to the database successfully.

---

### Phase 4: Implementing High Availability and Scalability

#### Task 1: Creating a Target Group
- Create a **Target Group** named `web-TG`.

#### Task 2: Creating an Application Load Balancer
- Create an **ALB** named `WEB-LB` and attach the `web-TG` targets.

#### Task 3: Implementing Auto Scaling
- Create a **Launch Template** named `template-web`.  
- Create an **Auto Scaling Group** named `web-auto` linked to the launch template.  
- Configure scaling policies based on CPU utilization or request count.

---

## ✅ Expected Outcome
By the end of the project:
- The web app is **fully functional**, **secure**, **scalable**, **highly available**, and **cost-effective**.  
- Users can **seamlessly manage student records** even under peak loads.  
- The design adheres to the **AWS Well-Architected Framework pillars**.

---
