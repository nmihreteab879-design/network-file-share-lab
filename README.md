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
The first step I took is connecting to a virtual machine I call dc-1 that will serve as the domain admin account and I also connected to a virtual machine I named client-1 which will serve as a normal user.
<img width="1528" height="1023" alt="image" src="https://github.com/user-attachments/assets/a85163a7-ab0d-48e5-a368-c21394c45df2" />

I then went into the dc-1(domain admin account) virtual machine and went to file explorer and pressed on windows(c:) and created 4 folders: read acess folder, write access folder, no acess folder and the accounting folder
<img width="1027" height="405" alt="image" src="https://github.com/user-attachments/assets/ef3993e5-a5e4-4c3f-9ec0-22208f7894bd" />

I then changed the access for the read acess to read by right clicking the read acess folder then I pressed properites and then pressed sharing and then share. I then typed domain users and gave the domain users read acess.
<img width="624" height="458" alt="image" src="https://github.com/user-attachments/assets/792d2f0a-5eb0-4321-ab83-e2eed6187e48" />

I then went to the write access folder and I right clicked  it pressed properities pressed sharing then I typed domain users and gave the domain users read/write permission.
<img width="593" height="457" alt="image" src="https://github.com/user-attachments/assets/cc3fe0d9-46e8-42e6-8dbf-8921e64e6386" />

I went to sharing for no acess group aswell and then I gave Domain Admins read/write access
<img width="617" height="458" alt="image" src="https://github.com/user-attachments/assets/1fcc6318-a136-4a23-a6cc-f73481bac6cf" />

I then went on client-1 and navigated to the shared folder by typing \\dc-1 in the search bar on files explorer. 
<img width="1125" height="640" alt="image" src="https://github.com/user-attachments/assets/18c40b5b-bb57-4b80-98e1-fcfac424b262" />

I also went to each folder and checked wether I would be able to acess it or not, aswell as wether or not I can write anthing inside the folder. I could view inside the read access folder but I could not write in it.
<img width="1130" height="637" alt="image" src="https://github.com/user-attachments/assets/e5326e9e-4f12-4228-ae73-3b88ce070597" />

In the write folder I could not only view inside the file but I could also add files and make changes to the folder
<img width="1128" height="636" alt="image" src="https://github.com/user-attachments/assets/ae506a96-0d71-4f89-9e28-a8684daafb91" />

In the no access folder I could not view anything inside the folder
<img width="1126" height="634" alt="image" src="https://github.com/user-attachments/assets/12a30058-701b-40c0-8b9d-8600fdadd3bb" />

I then opened active directory users and computers and created a organizational unit named _GROUPS I then created a group inside of the organizational unit called accountants
<img width="757" height="527" alt="image" src="https://github.com/user-attachments/assets/34024a35-6b35-4844-89ae-1d5991c89fa9" />

I then went back to accounting folder I made in the c drive and I right clicked it went to properites and the pressed sharing after that I add accountants and gave them read/write permission. 
<img width="1132" height="632" alt="image" src="https://github.com/user-attachments/assets/e92583e7-d353-4d81-821b-e75e40abc338" />

I then went back to the client-1(normal user) virtual machine to see what happens when I try to access the accounting folder and I was not able to get in
<img width="1127" height="638" alt="image" src="https://github.com/user-attachments/assets/6795a88d-d1e9-4807-9370-e42bc3a91a76" />

I then logged off of client-1(normal user) virtual machine then I went back to dc-1(domain admin) virtual machine and I went to active directory users and computers pressed on _groups then double clicked it and then pressed members and pressed add and then I added my user bic.voj 
<img width="750" height="512" alt="image" src="https://github.com/user-attachments/assets/2fa8392e-d93f-4726-886c-7c072e75b36f" />

I then signed back into to client-1 (normal user) as bic.voj and then I went to file explorer and typed \\dc-1 in the search bar and then pressed the accounting folder to see if I would be allowed acess and I was.
<img width="1129" height="635" alt="image" src="https://github.com/user-attachments/assets/45018873-91aa-45e5-91d4-012bcacb45fd" />




















