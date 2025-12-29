<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory File Share Permissions Lab</h1>
In this lab, I configured shared folders with different permission levels, created an AD security group, and validated access from a domain user. This demonstrates how organizations control access using Active Directory, security groups, and share permissions.<br />

<h2>Environments and Technologies Used</h2>

- Windows Server 2022 (Domain Controller)
- Windows 10 (Client Machine)
- Active Directory Users and Computers
- Windows File Explorer (Shared Folders)
- Remote Desktop Connection

<h2>Operating Systems Used</h2>

- Windows Server 2022  
- Windows 10 Pro

<h2>High-Level Steps</h2>

- Create shared folders with different access levels  
- Configure Share Permissions for Domain Users and Domain Admins  
- Test access from a domain-joined client  
- Create an AD Organizational Unit and Security Group  
- Assign folder permissions to the group  
- Add a user to the group and verify access  

<h2>Actions and Observations</h2>
The first step I took is connecting to a virtual machine I call dc-1 that will serve as the domain admin account and I also connected to a virtual machine I named client-1 which will serve as a normal user. By having both machines active, I can configure security settings on the domain controller and instantly test the results on the client workstation to ensure the network policies are functioning.

<img width="1528" height="1023" alt="image" src="https://github.com/user-attachments/assets/a85163a7-ab0d-48e5-a368-c21394c45df2" />

I then went into the dc-1(domain admin account) virtual machine and went to file explorer and pressed on windows(c:) and created 4 folders: read acess folder, write access folder, no acess folder and the accounting folder. This step is important because it establishes the baseline for the entire lab, providing separate areas where I can apply and test different security rules. By creating these specific folders, I am setting up a clear way to show how an administrator can control exactly what different employees can see or change on the company network.

<img width="1027" height="405" alt="image" src="https://github.com/user-attachments/assets/ef3993e5-a5e4-4c3f-9ec0-22208f7894bd" />

I then changed the access for the read acess to read by right clicking the read acess folder then I pressed properites and then pressed sharing and then share. I then typed domain users and gave the domain users read acess. This establishes a "view-only" environment, which is a standard security practice for information where you want employees to have the information but not the ability to edit it. By doing this, I've created a safe way to distribute data without risking the integrity of the original files.

<img width="624" height="458" alt="image" src="https://github.com/user-attachments/assets/792d2f0a-5eb0-4321-ab83-e2eed6187e48" />

I right-clicked the write folder, accessed the properties and sharing settings, and assigned permissions to the domain users group. This configuration is essential for collaborative environments where team members need to be able to create and update files. By granting these privileges, I enabled a workspace where data can be actively managed and edited by the general user population.

<img width="593" height="457" alt="image" src="https://github.com/user-attachments/assets/cc3fe0d9-46e8-42e6-8dbf-8921e64e6386" />

I went to sharing for no acess group aswell and then I gave Domain Admins read/write access. This is a critical security step used to isolate sensitive data so that only authorized accounts can interact with it. By only giving acces to domain admins I am excluding the Domain Users group, which ensures that any standard employee attempting to open this folder would be automatically blocked.

<img width="617" height="458" alt="image" src="https://github.com/user-attachments/assets/1fcc6318-a136-4a23-a6cc-f73481bac6cf" />

I navigated to the network path \\dc-1 from the client-1 workstation to test the permissions from a user's perspective. When I opened the read access folder, I confirmed that I could view the contents but was blocked from saving any changes or new files. This successfully demonstrates a "view-only" security policy
<img width="1125" height="640" alt="image" src="https://github.com/user-attachments/assets/18c40b5b-bb57-4b80-98e1-fcfac424b262" />
<img width="1130" height="637" alt="image" src="https://github.com/user-attachments/assets/e5326e9e-4f12-4228-ae73-3b88ce070597" />

In the write folder, I confirmed that I could view files and successfully create or edit new ones. This verifies that the read/write permissions are working as intended for a collaborative workspace.
When I tried to open the no access folder, I was immediately blocked by a security error. This proves the folder is properly restricted and only accessible to authorized administrators.

<img width="1128" height="636" alt="image" src="https://github.com/user-attachments/assets/ae506a96-0d71-4f89-9e28-a8684daafb91" />

<img width="1126" height="634" alt="image" src="https://github.com/user-attachments/assets/12a30058-701b-40c0-8b9d-8600fdadd3bb" />

I opened Active Directory Users and Computers and created an Organizational Unit named _GROUPS. Within that unit, I created a security group called accountants to manage departmental permissions. ensuring that all administrative groups are organized in one central location for easier access and maintenance.
<img width="757" height="527" alt="image" src="https://github.com/user-attachments/assets/34024a35-6b35-4844-89ae-1d5991c89fa9" />

I then went back to accounting folder I made in the c drive and I right clicked it went to properites and the pressed sharing after that I add accountants and gave them read/write permission. I then went back to the client-1(normal user) virtual machine to see what happens when I try to access the accounting folder and I was not able to get in. This occurs because the user is not yet a member of the newly created accountants group, so the system continues to deny entry.

<img width="1132" height="632" alt="image" src="https://github.com/user-attachments/assets/e92583e7-d353-4d81-821b-e75e40abc338" />

<img width="1127" height="638" alt="image" src="https://github.com/user-attachments/assets/6795a88d-d1e9-4807-9370-e42bc3a91a76" />

I logged off the client-1 workstation and returned to the dc-1 virtual machine to update the group membership. I opened Active Directory Users and Computers, navigated to the accountants group properties, and added the user bic.voj to the members list. This administrative change grants the user the necessary permissions to access the restricted accounting folder upon their next login.

<img width="750" height="512" alt="image" src="https://github.com/user-attachments/assets/2fa8392e-d93f-4726-886c-7c072e75b36f" />

I logged back into client-1 as bic.voj and navigated to the network path \dc-1 to verify the new permissions. Upon opening the accounting folder, I successfully gained access and could view the contents. This confirms that adding the user to the accountants group correctly applied the necessary permissions to their account.

<img width="1129" height="635" alt="image" src="https://github.com/user-attachments/assets/45018873-91aa-45e5-91d4-012bcacb45fd" />




















