# 1000-User-Active-Directory-Lab

## This lab uses Windows Server 2019 + Windows 10 to create a domain of 1000 users

### Techonlogies used: 
#### Windows Server 2019
#### Windows 10
#### Powershell scripting 

The diagram below represents the network and how the various components are linked: 

![Screenshot 2023-05-20 143607](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/427fc629-9fba-4b76-a0c0-1623c813625a)



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
Go to 'Add roles and features' and select 'Active Directory Domain Services' and install.

![Screenshot 2023-05-20 142530](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/09a0c955-5bac-4be6-9236-7101e3b61765)

Promote the server to DC status 

![Screenshot 2023-05-20 143746](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/ec73e178-1e47-44c3-92dd-191d452b11fb)

Create the domain name

![Screenshot 2023-05-20 143938](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/3e7232d5-1ecc-442f-bb23-70ab44ab3844)

