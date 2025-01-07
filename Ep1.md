## Q1. NGINX, Reverse Proxy, Proxy-Pass, and More

**NGINX**
- **Web Server**: Serves web pages to users when they visit a website.
- **Reverse Proxy Server**: Sits between users and servers to manage traffic.
- **Load Balancer**: Distributes user requests across multiple servers to ensure the website runs smoothly.

**NGINX Ingress Controller**
- Routes traffic from users to Kubernetes services inside the cluster.

**Reverse Proxy**
- Routes traffic from users to backend server.
  - **Flow**: `Client → Reverse Proxy → Backend Server`

**Proxy-Pass**
- Directive used in the NGINX configuration to forward incoming client requests to an upstream server.

---

## Q2. **SSL Encryption in Reverse Proxy NGINX**

Helps secure communication between the user and the proxy server.

**How it works**:
1. **Client to NGINX**: 
   - The client establishes an encrypted connection with NGINX using HTTPS (SSL/TLS).
2. **NGINX to Backend**: 
   - NGINX forwards the traffic to the backend server.
   - Can configure NGINX to terminate SSL (decrypt the traffic).

---

## Q3. **How to Automate Testing in DevOps Lifecycle**

Unit testing, incorporating testing into the CI/CD pipeline which improves the speed, quality, and reliability of the software.

---

## Q4. **DevOps KPIs**
KPI(Key Performance Indicators) - used to measure and track the success of DevOps initiatives.
- Deployment Frequency
- Change Failure Rate
- Customer Satisfaction (CSAT)
- Incident Frequency
- Cost of Downtime
- Infrastructure Utilization
- Deployment Time

---

## Q5. **Using Boto3 to Create an EC2 Instance**

[this blog](https://blog.knoldus.com/how-to-create-ec2-instance-using-python3-with-boto3/).

**Python Code Example**:
```python
import boto3

# Create a session using your AWS credentials
ec2 = boto3.resource('ec2')

# Create an EC2 instance
instance = ec2.create_instances(
    ImageId='ami-053b12d3152c0cc71',  # Replace with the desired AMI ID
    InstanceType='t2.micro',          # Choose an instance type, e.g., 't2.micro'
    MinCount=1,                       # Minimum number of instances
    MaxCount=1,                       # Maximum number of instances
    KeyName='kp2',                    # Replace with your key pair name
    SecurityGroupIds=['sg-0e22d57c96efa0013'], # Replace with your security group ID
)

# Print the instance ID of the created instance
print(f"EC2 instance created with ID: {instance[0].id}")
