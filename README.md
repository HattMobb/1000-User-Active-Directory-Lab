# 1000-User-Active-Directory-Lab

## This lab uses Windows Server 2019 + Windows 10 to create a domain of 1000 users

### Techonlogies used: 
#### Windows Server 2019
#### Windows 10
#### Powershell scripting 

The diagram below represents the network and how the various components are linked: 

IMAGE


### **A couple of things to note:**
### **The DC's INTERNAL NIC IP config is as follows:**

- IP: 172.16.0.1

- Subnet mask: 255.255.255.0

- DNS: 127.0.0.1

### **The DHCP settings of the DC are as follows:**

- Scope: 172.16.0.100-200

- Subnet mask: 255.255.255.0

- Gateway: 172.168.0.1

- DNS server: 172.16.0.1


### **The FQDN of the DC is my.domain.com**

### **Network Adress Translation on the DC allows every internal client to connect to the Internet**

---
## Setting up the domain
- Go to 'Add roles and features' and select 'Active Directory Domain Services' and install.
- ![Screenshot 2023-05-20 142530](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/09a0c955-5bac-4be6-9236-7101e3b61765)
