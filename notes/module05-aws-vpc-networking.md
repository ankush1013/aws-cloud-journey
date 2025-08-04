# AWS VPC and Networking

This module explains the concept of Virtual Private Cloud (VPC) in AWS, along with key networking components and services used to create secure, scalable, and highly available cloud architectures.

---

## ☁️ What is a VPC?

- A **VPC (Virtual Private Cloud)** is a logically isolated network in AWS.
- You define your own **IP address range** and deploy AWS resources (e.g., EC2, Load Balancers) inside this network.
- VPCs allow both **public** (internet-facing) and **private** (internal) resource deployment.

---

## 🧱 Subnets

- **Subnets** divide your VPC’s IP range into smaller sections.
- **Public subnet**: Internet-facing resources (like a web server).
- **Private subnet**: Resources not accessible from the public internet (like databases).
- Best practice: use **multiple subnets across Availability Zones (AZs)** for high availability.

---

## 🌐 Internet Gateway & NAT

- **Internet Gateway (IGW)**: A gateway attached to your VPC for public internet access.
  - Required for public subnets.
- **NAT Gateway**: Allows private subnets to **initiate outbound traffic** to the internet while remaining inaccessible from the outside.

---

## 📖 Route Tables

- A **Route Table** contains rules (routes) that determine how traffic flows within the VPC.
- You associate subnets with route tables.
- Public subnets require a route to the Internet Gateway:
  - Destination: `0.0.0.0/0`
  - Target: `IGW`

---

## 🔐 Security: NACLs vs Security Groups

| Feature            | Security Groups                   | Network ACLs                     |
|--------------------|------------------------------------|----------------------------------|
| Level              | Instance-level                     | Subnet-level                     |
| Type               | Stateful (remembers connections)   | Stateless (checks every packet) |
| Default behavior   | Deny all inbound, allow all outbound | Allow all traffic               |
| Rule evaluation    | Permits based on IP, port, protocol | Explicit allow/deny rules       |

---

## 🛡️ VPC Gateways

- **Internet Gateway**: Opens access to public internet.
- **Virtual Private Gateway (VGW)**: Connects AWS VPC to on-premises via **VPN**.
- **AWS Direct Connect**: Private, high-speed, dedicated fiber line between data center and AWS. Offers high throughput and reliability.

---

## 🌍 DNS and CDN Services

### Amazon Route 53
- DNS service that **translates domain names into IP addresses**.
- Offers routing policies:  
  - **Latency-based**  
  - **Geolocation**  
  - **Weighted round-robin**
- Can register domains directly.

### Amazon CloudFront
- AWS's **Content Delivery Network (CDN)**.
- Delivers content from **Edge Locations** (separate from Regions).
- Reduces latency and accelerates delivery of static & dynamic content.

---

## 🧠 Real-World Scenarios

- Companies often deploy **multi-VPC, multi-region** architectures.
- Use cases:
  - VPN + Direct Connect for secure on-premises-to-cloud communication.
  - CloudFront + Route 53 for global content delivery.
  - Redundant private and public subnets for high availability.
- **Direct Connect + VPN** can be used for **failover**, **compliance**, or **performance boosts**.

---

## 📌 Summary

- AWS VPC provides fine-grained control over cloud networking.
- Use **subnets**, **route tables**, and **gateways** to define traffic flow.
- Use **Security Groups** and **Network ACLs** to control access at different layers.
- Services like **Route 53**, **CloudFront**, **VPN**, and **Direct Connect** support secure, fast, and global networking.

---

✅ **Module 5 complete**. Next up: Identity and Access Management (IAM).
