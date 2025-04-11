# Active Directory Corporate Simulation Using Oracle VirtualBox

<img width="801" alt="Screenshot 2023-12-22 at 11 33 09 PM" src="https://github.com/EricMcclellan1/AD-Lab/assets/147299619/d2b3b411-5a6f-43d2-ab21-7b1b3bc114af">

 ## Summary

 In this project, I built an Active Directory home lab using Oracle VirtualBox to simulate a corporate environment with 1,000 users. The environment consisted of a Windows Server 2019 virtual machine acting as the Domain Controller, and a Windows 10 Pro virtual machine serving as the client machine.

To replicate a corporate structure, I used a custom PowerShell script to populate Active Directory with 1,000 users. Each user was assigned a unique username—consisting of the first letter of their first name followed by their last name—as well as a default password. Finally, the Windows 10 Pro client machine was configured and successfully joined to the domain.



![image](https://github.com/user-attachments/assets/9a2b777c-d910-44e9-93b4-17af56651f37)



 Next, I used Active Directory to create Group Policies, Security Groups, and Organizational Units. In conclusion, Active Directory was configured to serve as a centralized management system for computers, user accounts, and other network resources. 


## Technologies and Components Used:

-	Windows Server 2019
-	Windows 10 Pro
-	Oracle VirtualBox
-	Active Directory
-	Active Directory Domain Service
-	Network Address Translation (NAT)
-	Domain Name Service (DNS)
-	Dynamic Host Configuration Protocol (DHCP)
-	File and Storage Services
-	Internet Information Services (IIS)
-	PowerShell


## VirtualBox Set-up

 I used VirtualBox to create both the Domain Controller (DC) and the client machine. The client machine was created after the Domain Controller was fully set up and the 1,000 users had been added.

![1 DC VM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/05ee237c-3f07-4c7b-a2ac-61a7e2cc1a10)

![2 CLIENT VM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/ee771bb1-0c2e-417d-8726-427fe1d26ec7)



## Windows Server 2019 and Active Directory Configuration

 Two network adapters were used to separate internal and external traffic. To make them easily identifiable, they were renamed to _Internet_ for external traffic and X_Internal_X for internal traffic.

![3 network ](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/14fde5ab-94a8-40fb-9816-a399d908550b)

![Screenshot 2023-12-22 at 11 15 02 PM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/755917c5-e5b2-4293-88b4-ff2920a21b1a)

![Screenshot 2023-12-22 at 11 15 29 PM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/afd41583-cd29-4d9e-a721-f7bf9859f698)


 In addition, various roles and services within Active Directory and the Domain Controller were configured.

![Screenshot 2023-12-22 at 11 16 26 PM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/680e892c-bf21-4050-8f17-806c51ebd4cf)



 A custom name list containing 1,000 fake names was used, saved in a text document. To make it more realistic, I included my own name at the top of the list.


![image](https://github.com/user-attachments/assets/1a159fe5-45b8-4d77-8a8b-cc9edee1ab6a)


 A custom PowerShell script was then executed in conjunction with the name list to populate Active Directory. The script parsed the list and created user accounts using a naming convention based on the first letter of the first name combined with the last name.


![6 powershell 1](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/a027ef81-82c5-429d-ac14-d35c7333fe42)

![6 powershell 2](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/7a926f67-b162-464c-90d2-139fe2879f39)

![7 powershell users](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/cc8bcfb8-a8a9-41ab-b7c1-d5824dc025c5)


 ![image](https://github.com/user-attachments/assets/f925390a-23df-418e-afcf-c70d5e81d845)


## Joining Windows 10 Pro To The Domain Controller

As mentioned earlier, I also used VirtualBox to create a Windows 10 Pro environment to serve as a proxy for a real-life client computer. The network adapter was set to “Internal Network” to ensure that all traffic flowed exclusively through the Domain Controller. To verify connectivity, I pinged the previously created Domain Controller, “mydomain.com,” and received a successful response.

After joining the client machine to the Domain Controller, I tested the setup by logging into the Windows 10 VM using credentials from 10 of the previously generated user accounts. This simulated the experience of new employees accessing the corporate network for the first time. Each login attempt was successful.

![image](https://github.com/user-attachments/assets/cbfc48c2-10ea-4678-8abc-f21b08afb07d)

![image](https://github.com/user-attachments/assets/3c4897c0-7092-4304-883d-bc1526d8fd00)

![image](https://github.com/user-attachments/assets/7ff0b85f-6534-4b75-85d5-1ca701f75906)

## Conclusion

In conclusion, this project provided valuable experience in properly configuring Active Directory, while also enhancing my practical skills with scripting and VirtualBox. Through hands-on exploration, I gained deeper technical insight into Active Directory—its features, functions, and overall structure—broadening my understanding of how it's used in real-world corporate environments.







