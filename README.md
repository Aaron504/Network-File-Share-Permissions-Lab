

<h1>Network File Share Permissions Lab</h1>
This repository contains a comprehensive guide and resources for setting up network file shares and configuring permissions in a hybrid Active Directory environment. The lab covers step-by-step instructions for creating, managing, and securing network file shares, ensuring proper access control and permissions.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Contents</h2>

- Overview of network file sharing
- Creating network file shares
- Configuring permissions and access control
- Integrating file shares with Azure AD
- Testing and verifying file share access
- Troubleshooting common issues

<h2>High Level Configuration Steps</h2>

- Create some sample file shares with various permissions
- Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)
- Connect/log into Client-1 as a normal user (mydomain\<someuser>) (random user from AD)
- On DC-1, on the C:\ drive, create 4 folders: “read-access”, “write-access”, “no-access”, “accounting”
- Set the following permissions (share the folder) for the “Domain Users” group:
- Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
- Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”
- Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”
![Screenshot 2024-07-18 183438](https://github.com/user-attachments/assets/13b089b7-4b67-408e-9603-5f7ab2a19c98)
![Screenshot 2024-07-18 184137](https://github.com/user-attachments/assets/620ea2f0-5be5-4036-806e-55e87bc8d365)
![Screenshot 2024-07-18 184711](https://github.com/user-attachments/assets/6ca866df-08e9-4233-bab6-b7f67e158257)
![Screenshot 2024-07-18 185238](https://github.com/user-attachments/assets/4437ba73-a53a-491b-b90d-175972279286)
![Screenshot 2024-07-18 185513](https://github.com/user-attachments/assets/92551073-cb9d-48f6-86e8-d945e06ac548)
![Screenshot 2024-07-18 185826](https://github.com/user-attachments/assets/79d049db-81b2-4eb6-ad3d-cab20d346c41)

- Attempt to access file shares as a normal user
- On Client-1, navigate to the shared folder (start, run, \\dc-1)
- Try to access the folders you just created. Which folders can you access? Which folders can you create stuff in? Does it make sense?
![Screenshot 2024-07-18 190901](https://github.com/user-attachments/assets/56e086ae-b9b6-4b3c-b8cf-77f6f3e8253d)
![Screenshot 2024-07-18 191039](https://github.com/user-attachments/assets/aba61486-e1c4-4699-9b9c-53c034eef441)
![Screenshot 2024-07-18 191147](https://github.com/user-attachments/assets/a25fee17-7321-47a7-901f-e5da01360bed)
![Screenshot 2024-07-18 191252](https://github.com/user-attachments/assets/a197cea8-9f7d-4a53-9b0e-4dfc582809c8)

- Create an “ACCOUNTANTS” Security Group, assign permissions, an test access
- Go back to DC-1, in Active Directory, create a security group called “ACCOUNTANTS”
- On the “accounting” folder you created earlier, set the following permissions:
- Folder: “accounting”, Group: “ACCOUNTANTS”, Permissions: “Read/Write”
- On Client-1, as  <someuser>, try to access the accountants folder. It should fail. 
- Log out of Client-1 as  <someuser>
- On DC-1, make <someuser> a member of the “ACCOUNTANTS”  Security Group
- Sign back into Client-1 as <someuser> and try to access the “accounting” share in \\DC-1\ - Does it work now?
![Screenshot 2024-07-18 192332](https://github.com/user-attachments/assets/d16ef364-b1e3-4ae0-9252-ce0eca62bffe)
![Screenshot 2024-07-18 192807](https://github.com/user-attachments/assets/fe4fde39-e7e9-4598-86ec-a5f1f125d75c)
![Screenshot 2024-07-18 193056](https://github.com/user-attachments/assets/62878b22-336b-492c-b96a-d01399aedf8c)
![Screenshot 2024-07-18 193414](https://github.com/user-attachments/assets/1a8efdf8-c261-4ecf-ba6d-c2941343c601)
![Screenshot 2024-07-18 194204](https://github.com/user-attachments/assets/d8480bfa-4fe8-4211-8a3e-41c82eeff9a4)






















