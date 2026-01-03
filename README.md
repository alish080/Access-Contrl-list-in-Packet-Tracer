# Access-Contrl-list-in-Packet-Tracer
Implementing ACL in Packet Tracer
# Access Control List (ACL) Implementation – Cisco Packet Tracer Lab

## 📌 Overview

This project demonstrates the **implementation of Standard Access Control Lists (ACLs)** using **Cisco Packet Tracer**. The goal of this lab is to understand how routers control traffic between different networks using ACL rules such as **permit** and **deny**.

This lab is beginner‑friendly and designed for:

* CCNA students
* Networking fundamentals learners
---

## 🧠 Lab Objectives

* Understand why **different IP networks** are used
* Configure **router interfaces** with IP addresses
* Learn the role of **default gateway**
* Implement **Standard ACLs** on router interfaces
* Control traffic using **permit** and **deny** rules
* Visualize packet flow in a small network

---

## 🗺️ Network Topology

The lab consists of:

* **1 Router**
* **1 Switch**
* **3 PCs**

### IP Addressing Scheme

| Device | Interface | IP Address   | Network         |
| ------ | --------- | ------------ | --------------- |
| PC0    | NIC       | 192.168.10.2 | 192.168.10.0/24 |
| Router | G0/0      | 192.168.10.1 | 192.168.10.0/24 |
| PC1    | NIC       | 10.0.0.2     | 10.0.0.0/24     |
| PC2    | NIC       | 10.0.0.3     | 10.0.0.0/24     |
| Router | G0/1      | 10.0.0.1     | 10.0.0.0/24     |

---

## 🔧 Router Configuration (Summary)

### Interface Configuration

```bash
interface GigabitEthernet0/0
 ip address 192.168.10.1 255.255.255.0
 no shutdown

interface GigabitEthernet0/1
 ip address 10.0.0.1 255.255.255.0
 no shutdown
```

### Standard ACL Configuration

```bash
access-list 1 deny host 10.10.10.2
access-list 1 permit host 10.10.10.3

interface GigabitEthernet0/1
 ip access-group 1 in
```

📌 **Note:** ACLs are evaluated top‑down and end with an implicit `deny any`.

---

## 🔐 What This ACL Does

* ❌ Blocks traffic from **10.10.10.2**
* ✅ Allows traffic from **10.10.10.3**
* ❌ Blocks all other sources (implicit deny)

The ACL is applied **inbound** on `GigabitEthernet0/1`, filtering traffic as it enters the router.

---

## 🎥 Video Explanation

A complete **step‑by‑step video explanation** of this lab is provided, covering:

* Topology visualization
* IP addressing logic
* ACL logic (permit vs deny)
* Packet flow explanation

📺 **Video Link:** *(add your YouTube link here)*
https://youtu.be/e-0xJ0wJAjQ

---

## 📁 Project Files Included

* 📄 **PDF** – Detailed lab documentation and explanation
* 📝 **DOCX** – Written report / assignment version
* 🌐 **PKT** – Cisco Packet Tracer lab file

You can download and open the `.pkt` file directly in **Cisco Packet Tracer**.

---

## 🚀 How to Use This Lab

1. Download all files from this repository
2. Open the `.pkt` file in Cisco Packet Tracer
3. Review the topology and device configurations
4. Test connectivity using `ping`
5. Observe ACL behavior
6. Watch the video for full explanation

---

## 🎯 Key Learning Takeaways

* Routers connect **different networks**
* Switches connect **devices within the same network**
* ACLs provide **basic network security**
* `permit` and `deny` are the only ACL actions
* Default gateway belongs to **hosts**, not routers

---

## 📬 Contact

If you have questions or suggestions:

* GitHub Issues
* YouTube comments

⭐ If this project helped you, consider giving it a star!

-- ALISH 
