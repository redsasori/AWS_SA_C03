## **CIDR (Classless Inter-Domain Routing)**

 **IP Blueprint**  
Defines **how BIG** the network is and **how IPs are grouped**

---

## **IPv4 Basics (Lock This In)**

- IPv4 = **32 bits total**
    
- Format: `x.x.x.x`
    
- Each number = **8 bits**
    

```
8 + 8 + 8 + 8 = 32 bits
```

---

## **CIDR Meaning (Very Important)**

> **CIDR = how many bits are LOCKED**

- `/16` → **First 16 bits fixed**
    
- Remaining **16 bits = IP combinations**
    

### Example:

```
VPC: 10.0.0.0/16
```

- **10.0** → LOCKED (cannot change)
    
- **x.x** → FREE (used for IP allocation)
    

---

## **Subnet Example (Why This Works)**

```
10.0.1.0/24  ✅
```

- Inside `10.0.0.0/16`
    
- Subnet range is **smaller than VPC**
    

❌ Invalid:

```
10.1.0.0/24
```

- Breaks the locked `10.0` boundary
    
- **Outside VPC range**
    

> **Subnet must LIVE inside the VPC**

---

## **WHY CIDR? → S.A.F.E.R (Memory Code)**

- **S – Size control**  
    `/16` big | `/24` medium | `/28` small
    
- **A – Avoid IP waste**  
    No unused blocks
    
- **F – Flexible subnetting**  
    Separate Web / App / DB
    
- **E – Efficient routing**  
    Smaller route tables
    
- **R – Range planning**  
    Scale without overlap
    

---

## **HOW CIDR Works**

- Format:
    

```
IP / Prefix
```

- Example:
    

```
10.0.0.0/16
```

### **Prefix Rule**

> Smaller prefix number → **Bigger network**

---

## **CIDR in AWS VPC (Exam Critical)**

- CIDR is **mandatory**
    
- Example:
    

```
VPC → 10.0.0.0/16
```

- Subnets must be inside:
    

```
10.0.1.0/24
10.0.2.0/24
```

---

## **Golden Rules (Never Forget)**

- VPC CIDR → **hard to change**
    
- Subnet CIDR → **smaller than VPC**
    
- **No overlapping CIDRs**
    
- AWS reserves **5 IPs per subnet**
    

---

## **AWS Reserved IPs (Fixed Fact)**

AWS keeps 5 IPs for:

- Network address
    
- Router
    
- DNS
    
- Future use
    
- Broadcast (AWS internal)
    

---

## **Usable IP Formula (Memorize This)**

```
Usable IPs = (2^(32 − CIDR)) − 5
```

---

## **Mental Picture (Best Recall)**

**CIDR = Land**  
**VPC = City**  
**Subnet = Sector**  
**IP = House**

---

## **One-Line Recall**

> **CIDR locks part of a 32-bit IP to define network size and allows flexible, efficient subnetting inside a VPC.**