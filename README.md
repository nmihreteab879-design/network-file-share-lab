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



















