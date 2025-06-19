# Network File Shares and Permissions
---
In this lab we are going to setup network folder share and permissions
---

## Create some sample file shares with various permissions
### Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)
### Connect/log into Client-1 as a normal user (mydomain\<someuser>)
### On DC-1, on the C:\ drive, create 4 folders: “read-access”, “write-access”, “no-access”, “accounting”

![step1](https://github.com/user-attachments/assets/2b61c318-387c-47d2-80ee-0acbc833b383)
![step2](https://github.com/user-attachments/assets/adae4b46-2b6a-43eb-999d-3605b8bd8057)

## Set the following permissions (share the folder)
### Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
### Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”
### Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”
### (Skip accounting for now)
![step3](https://github.com/user-attachments/assets/f73486fa-8dba-4fa8-991f-57bdb315589f)
![step4](https://github.com/user-attachments/assets/79f485ea-c711-4fc0-8baf-99e34942baeb)
![step5](https://github.com/user-attachments/assets/630c2517-dc70-4897-bd78-ff960692f30b)

### Attempt to access file shares as a normal user
### On Client-1, navigate to the shared folder (start, run, \\dc-1)
![step6](https://github.com/user-attachments/assets/835f586e-a47c-4590-9a12-cf0565308af1)

### Try to access the folders you just created. Which folders can you access? Which folders can you create stuff in? Does it make sense?
![step7](https://github.com/user-attachments/assets/45a04e68-e49c-4514-98f3-d0da25c28908)
![step8](https://github.com/user-attachments/assets/afe3ba19-c07b-46e0-a7bb-7335c3a82f97)
![step9](https://github.com/user-attachments/assets/06909a8b-5e10-454c-8cb7-c351c8132a8c)
### Login as an Admin and try to create a folder or file
![step10 admin](https://github.com/user-attachments/assets/938638bd-f2ce-42b5-861c-87f6c046e15e)

### Create an “ACCOUNTANTS” Security Group, assign permissions, an test access
![step 11](https://github.com/user-attachments/assets/335111e4-722b-4804-9c75-a6120ff98158)
![step12](https://github.com/user-attachments/assets/7406adb9-7795-4df4-85dd-77a03ffd16d4)
![step13](https://github.com/user-attachments/assets/4af85398-e366-487c-b771-d8f68a313dba)
![step14](https://github.com/user-attachments/assets/a785d0e5-cc96-4d14-9bc6-ba30c20442a8)

### Go back to DC-1, in Active Directory, create a security group called “ACCOUNTANTS”
### On the “accounting” folder you created earlier, set the following permissions:
### Folder: “accounting”, Group: “ACCOUNTANTS”, Permissions: “Read/Write”
![step15](https://github.com/user-attachments/assets/9636eef5-d1dc-4a57-b419-81c06cca2709)

### On Client-1, as  <someuser>, try to access the accountants folder. It should fail. 
![step16](https://github.com/user-attachments/assets/46ceac46-b5a3-4852-ac65-5ee3e8659e6a)

### Log out of Client-1 as  <someuser>
### On DC-1, make <someuser> a member of the “ACCOUNTANTS”  Security Group
![step17](https://github.com/user-attachments/assets/d8874844-5dab-43db-92d2-3f0d7f7631f5)
![step18](https://github.com/user-attachments/assets/e5b72640-893c-4e07-90ca-c6267c1b4fc0)

### Sign back into Client-1 as <someuser> and try to access the “accounting” share in \\DC-1\ - Does it work now?
![step19](https://github.com/user-attachments/assets/ab822af7-06c9-4ba7-a827-f206c0610c81)

