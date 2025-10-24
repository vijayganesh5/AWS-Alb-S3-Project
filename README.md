# ⚖️ AWS Load Balancer & S3 Monitoring Project

## 🎯 Project Objective
Create a secure S3 bucket with CloudWatch logging and deploy an Application Load Balancer with two EC2 instances.

## 🏗️ Architecture Overview
```
Users 🌍
    ↓
Application Load Balancer ⚖️
    ├── EC2 Instance 1 🐧
    └── EC2 Instance 2 🐧
        ↓
    S3 Bucket (Private) 📦
        ↓
    CloudWatch Logs 📊
```

## 🛠️ Tech Stack
- **AWS S3** - Secure File Storage
- **AWS EC2** - Web Servers
- **Application Load Balancer** - Traffic Distribution
- **CloudWatch** - Logging & Monitoring

## 🚀 Implementation Steps

### Part 1: Secure S3 Bucket with CloudWatch Logging

#### 1. Create S3 Bucket
- Create bucket with **Block ALL Public Access** enabled
- Enable server access logging
- Configure bucket policy for private access

#### 2. Set Up CloudWatch Logs
- Create CloudWatch log group
- Configure S3 to send access logs to CloudWatch
- Upload test files to verify logging

### Part 2: Load Balancer with EC2 Instances

#### 1. Launch EC2 Instances
- Launch **two Linux instances** with web servers (Apache/Nginx)
- Install web server and create custom index pages
- Configure security groups for HTTP traffic

#### 2. Create Application Load Balancer
- Create ALB in appropriate subnets
- Configure target group with both EC2 instances
- Set up health checks
- Verify load balancer IP in server responses

## 📁 Project Structure
```
aws-alb-s3-project/
├── README.md
└── Project-Steps.txt
```

## ⚙️ Configuration Details

### S3 Bucket Settings
- **Public Access**: Block all public access
- **Versioning**: Enabled (optional)
- **Logging**: Server access logging enabled
- **Bucket Policy**: Restrictive policy

### EC2 Instances
- **OS**: Amazon Linux 2
- **Web Server**: Apache/Nginx
- **Custom Index**: Display instance ID + Load Balancer IP
- **Security Group**: Allow HTTP (port 80)

### Application Load Balancer
- **Type**: Application Load Balancer
- **Listeners**: HTTP (port 80)
- **Target Group**: Both EC2 instances
- **Health Checks**: Configured

## 📋 Submission Requirements

### 📸 Required Screenshots:
1. **S3 Bucket** - Showing private configuration
2. **File Upload** - Files uploaded to S3
3. **CloudWatch Logs** - Access logs for uploaded files
4. **EC2 Instances** - Two instances running
5. **Load Balancer** - ALB configuration and health checks
6. **Load Balancer IP Output** - Web response showing ALB IP

### 🔗 URLs to Submit:
- GitHub Repository URL

## 🎯 Success Criteria
- ✅ S3 bucket created with no public access
- ✅ Files uploaded and CloudWatch logs visible
- ✅ Two EC2 instances launched and healthy
- ✅ Application Load Balancer configured
- ✅ Web output shows Load Balancer IP address
- ✅ Traffic properly distributed between instances

## 💡 Implementation Tips

### For S3 & CloudWatch:
- Use unique bucket names
- Enable access logging in bucket properties
- Check CloudWatch log streams for upload events

### For Load Balancer:
- Create instances in different AZs for high availability
- Configure web servers to show ALB IP in responses
- Use `curl` or browser to verify load balancing

### Verification Commands:
```bash
# Check which instance is responding
curl http://your-alb-dns-name

# Verify CloudWatch logs
aws logs describe-log-streams --log-group-name your-log-group
```

## 🎉 Output Link with Screenshots:
- https://docs.google.com/document/d/10TVfdved1XEsgtzYiRFFbqz7Ek4Grqk_FhXu8AduBdg/edit?usp=sharing

---

