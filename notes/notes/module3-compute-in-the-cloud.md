# Module 3: Compute in the Cloud

## Amazon EC2
- **EC2** = Virtual servers (instances) in the AWS cloud.
- **Use cases:** From basic websites to high-performance workloads.
- **Unmanaged service** – you manage OS, patching, scaling.
- AWS handles the infrastructure (Shared Responsibility Model).

---

## Managed vs Unmanaged Services

| Type       | Example | Responsibility                        |
|------------|---------|----------------------------------------|
| Unmanaged  | EC2     | You manage everything above hardware. |
| Managed    | ELB, SNS, SQS | AWS manages most tasks. You focus on your app. |

- **Analogy:**
  - _Unmanaged_ = espresso machine (customized, effort)
  - _Managed_ = coffee pod machine (easy, fast)

---

## Serverless Computing

- No infrastructure visibility.
- AWS handles provisioning, scaling, and maintenance.
- **Example:** AWS Lambda
- You focus only on code logic.

---

## Lambda Example: Triggered by SQS

- **Architecture:** SQS queue → Lambda function
- Steps:
  1. Create an SQS queue.
  2. Use Lambda blueprint (Node.js runtime shown).
  3. Assign execution role (permissions).
  4. Lambda reads messages and logs them (via CloudWatch).

---

## Containers

- Solve "it works on my machine" issue.
- Package: app + runtime + dependencies in 1 unit.
- **Benefits:** Portability, fast startup, efficient resource use.

### Hosting Containers on AWS

- **ECS (Elastic Container Service)** – Simple orchestration.
- **EKS (Elastic Kubernetes Service)** – Full Kubernetes power.
- **ECR (Elastic Container Registry)** – Store container images.

### Compute Options for Containers

| Option  | Control   | Managed by |
|---------|-----------|-------------|
| EC2     | High      | You         |
| Fargate | Serverless| AWS         |

### Container Workflow
1. Upload image to ECR.
2. Choose ECS or EKS to manage it.
3. Run it on EC2 or Fargate.

---

## Other AWS Compute Services

### Elastic Beanstalk
- Deploy apps easily.
- Handles EC2, networking, scaling, and ELB for you.

### AWS Batch
- Run large-scale data processing or simulations.
- AWS manages scaling + infrastructure.

### Amazon Lightsail
- Simple, low-cost VM + web hosting.
- Great for blogs, personal apps, quick MVPs.

### AWS Outposts
- Hybrid cloud service.
- Run AWS services **on-premises** with AWS hardware.
- Ideal for low-latency or local data residency needs.

---
