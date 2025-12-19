### **VPC = Virtual Private Cloud**

- **Virtual network** inside AWS
    
- **Region-locked** → exists in **ONE AWS Region only**
    
- Like an **on-prem data center network**, but **cloud-scale & low cost**
    

---

### **Core Building Blocks (Think: C-R-S-S-S)**

**[[CIDR]]** block  
**R**oute table (main + custom)  
**S**ubnets  
**S**ecurity Groups  
**S**ecurity (NACLs)

---

### **Availability Zones (AZs)**

- AZ = **one or more physical data centers**
    
- **VPC spans multiple AZs**
    
- **High availability by design**
    

---

### **Subnets — Golden Rule**

> **One Subnet = One AZ**

- Subnet **cannot span AZs**
    
- Multiple subnets **can exist in the same AZ**
    
- Instances in the **same subnet talk freely**
    

---

### **Routing Logic**

- **Same subnet** → auto communication
    
- **Different subnet** → needs **Route Table**
    
- **All subnets are interconnected by default**
    
- Custom route tables can override behavior
    

---

### **Public vs Private Subnets**

- **Public Subnet**
    
    - Internet-facing
        
    - Web servers, Bastion hosts
        
- **Private Subnet**
    
    - No Internet access
        
    - Databases, backend apps
        

---

### **Traffic Security (Two Layers)**

- **Security Groups** → Instance-level firewall (STATEFUL)
    
- **NACLs** → Subnet-level firewall (STATELESS)
    

---

### **One-Line Recall**

> **Amazon VPC is a region-scoped virtual network that spans multiple AZs, uses CIDR + routing + subnets, and controls traffic with Security Groups and NACLs.**