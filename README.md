The first step I took is connecting to a virtual machine I call dc-1 that will serve as the domain admin account and I also connected to a virtual machine I named client-1 which will serve as a normal user.
<img width="1528" height="1023" alt="image" src="https://github.com/user-attachments/assets/a85163a7-ab0d-48e5-a368-c21394c45df2" />

I then went into the dc-1(domain admin account) virtual machine and went to file explorer and pressed on windows(c:) and created 4 folders: read acess folder, write access folder, no acess folder and the accounting folder
<img width="1027" height="405" alt="image" src="https://github.com/user-attachments/assets/ef3993e5-a5e4-4c3f-9ec0-22208f7894bd" />

I then changed the access for the read acess to read by right clicking the read acess folder then I pressed properites and then pressed sharing and then share. I then typed domain users and gave the domain users read acess.
<img width="624" height="458" alt="image" src="https://github.com/user-attachments/assets/792d2f0a-5eb0-4321-ab83-e2eed6187e48" />

I then went to the write access folder and I right clicked  it pressed properities pressed sharing then I typed domain users and gave the domain users read/write permission.
<img width="593" height="457" alt="image" src="https://github.com/user-attachments/assets/cc3fe0d9-46e8-42e6-8dbf-8921e64e6386" />

I went to sharing for no acess group aswell and then I gave domain admins read/write access
<img width="617" height="458" alt="image" src="https://github.com/user-attachments/assets/1fcc6318-a136-4a23-a6cc-f73481bac6cf" />



