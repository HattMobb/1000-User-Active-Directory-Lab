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
## Setting up the domain + networking features
Go to 'Add roles and features' and select 'Active Directory Domain Services' and install.

![Screenshot 2023-05-20 142530](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/09a0c955-5bac-4be6-9236-7101e3b61765)

Promote the server to DC status 

![Screenshot 2023-05-20 143746](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/ec73e178-1e47-44c3-92dd-191d452b11fb)

Create the domain name

![Screenshot 2023-05-20 143938](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/3e7232d5-1ecc-442f-bb23-70ab44ab3844)

For improved organistion, create a personal admin account within an OU in 'Users and Computers' - 

![Screenshot 2023-05-20 150518](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/9b8d603d-4652-432c-ad43-2d4c703d3d9a)

Don't forget to add the account to the admin group within the account properties 

![Screenshot 2023-05-20 150944](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/04663860-8a11-406c-a10e-e1b41e3e85a2)

Logging into your personal admin account, Network Address Translation and Remote Access can be installed to allow any clients on the network to connect to the internet via the DC.
RAS (ENSURE ROUTING IS CHECKING WHLILE GOING THROUGH OPTIONS MENU:

![Screenshot 2023-05-20 151329](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/52d21b03-f42a-4a26-aa07-e21fd1e75b31)

Once installed, go to Tools - Routing and Remote Access - DC - Configure and check NAT to enable (make sure to tick your INTERNET FACING NIC when prompted for the adapter to use for Internet access).

![Screenshot 2023-05-20 151730](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/ae38f4cd-1963-4113-99ee-02cad8dec0f2)

Finally, to serve clients usable IP address', add DCHP to the DC and configure the scope(address range) that the server can use.

![Screenshot 2023-05-20 152438](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/5d47a798-2313-4da3-ba3d-bc4bce53cc1e)

As noted above, this scope will allow the server to issue adresses in the range 172.16.0.100 - 172.16.0.200
Add the adderess of the DC INTERNAL NIC as the default gateway ( it has both routing and NAT configured)
Installing Active Directory on the server allows it to also act as a DNS Server so add the DC address as the DNS server when prompted.
![Screenshot 2023-05-20 152740](https://github.com/HattMobb/1000-User-Active-Directory-Lab/assets/134090089/9ce16049-197e-4cd8-8181-842318641a4f)



Any connected clients will now have internet access!
