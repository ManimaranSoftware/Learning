### Amazon VPC

- VPC (Virtual Private Cloud) - Isolated virtual network for AWS resources.

---

### Subnet

- Subnet - Logical division of a VPC.
- Types - Public Subnet, Private Subnet.

---

### Internet Gateway (IGW)

- Enables communication between a VPC and the internet.

---

### NAT Gateway

- Allows resources in a private subnet to access the internet.
- Prevents inbound internet connections.

---

### Route Table

- Defines how network traffic is routed within a VPC.

---

### Security Group

- Virtual firewall for EC2 instances.
- Controls inbound and outbound traffic.
- Stateful.

---

### Network ACL (NACL)

- Firewall at the subnet level.
- Controls inbound and outbound traffic.
- Stateless.

---

### IAM (Identity and Access Management)

- Manages users, groups, roles and permissions in AWS.

---

### IAM Role

- Temporary permissions assigned to AWS resources.
- Commonly used by EC2 and Lambda.

---

### IAM Policy

- JSON document defining permissions for AWS resources.

---

### AWS KMS

- Key Management Service.
- Manages encryption keys.

---

### AWS Secrets Manager

- Securely stores and manages secrets such as passwords and API keys.

---

### Benefits

- Secure networking.
- Fine-grained access control.
- Data encryption.
- Network isolation.
- Secure resource access.

---

## Small improvement 💡

Let's also add:

### Public vs Private Subnet

- **Public Subnet** → Has direct internet access.
- **Private Subnet** → No direct internet access.