<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial showcases setting up Active Directory in Azure and deploying domain services, including configuration of user accounts and Group Policy.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 

## Table of Contents
- [Setting up Active Directory in Azure](#setting-up-active-directory-in-azure)
- [Deploy Active Directory Steps](#deploy-active-directory-steps)


<h2>##Setting up Active Directory in Azure</h2>

<p>
<img width="1455" height="780" alt="image" src="https://github.com/user-attachments/assets/2ece5062-3d2b-4c84-b3ff-353022981cd4" />
<img width="1453" height="780" alt="image" src="https://github.com/user-attachments/assets/bf186555-524b-480d-94f4-7058ecc5a480" />
<img width="1453" height="778" alt="image" src="https://github.com/user-attachments/assets/2a06bd3c-e708-4754-890b-772562944e1c" />


</p>
<p>
Change the private IP address on DC-1 from dynamic to static to ensure consistent network identification.
</p>
<br />

<p>
<img width="1455" height="780" alt="image" src="https://github.com/user-attachments/assets/5a5dcf2f-4c9c-436c-b9fb-9f96a8ee4933" />
<img width="1453" height="779" alt="image" src="https://github.com/user-attachments/assets/e757a6c4-bba3-41a1-a09b-b6a46c1de841" />
<img width="1454" height="781" alt="image" src="https://github.com/user-attachments/assets/f7026cc5-49e4-412e-ae16-108414e0a9c6" />

</p>
<p>
Set Client-1’s DNS server to the private IP address of DC-1 so the system can resolve Active Directory and internal network resources.
</p>
<br />

<p>
<img width="1452" height="780" alt="image" src="https://github.com/user-attachments/assets/159ee708-6282-447c-96dc-e4d94f0ccf87" />
<img width="1457" height="779" alt="image" src="https://github.com/user-attachments/assets/d4a100e1-b0ae-4892-a42c-a911c501477e" />

</p>
<p>
Log into Client-1 and use ping to confirm it can successfully reach DC-1’s private IP address.

Run ipconfig /all on Client-1 to confirm that the DNS server is correctly set to DC-1’s IP address.
</p>
<br />


<p>
<img width="1387" height="781" alt="image" src="https://github.com/user-attachments/assets/fb7ce4a0-a77b-4bff-b4e7-ffd3bb390199" />


</p>

<p>
Sign in to DC-1, run ipconfig /all, and review the DNS server values to see how they differ from the configuration on Client-1.
</p>
<br />


<h2>##Deploy Active Directory Steps</h2>



<p>
<img width="1456" height="777" alt="image" src="https://github.com/user-attachments/assets/2b17b26f-a3ef-4ffa-935c-32641817d355" />
<img width="1460" height="779" alt="image" src="https://github.com/user-attachments/assets/9ccd748c-60bc-4dac-a590-19a9795a2ef1" />
<img width="1455" height="780" alt="image" src="https://github.com/user-attachments/assets/4ad0637f-943b-4662-a7ce-385b0ef80cde" />
<img width="1456" height="778" alt="image" src="https://github.com/user-attachments/assets/5615c2a6-4f02-4774-be23-e51eac357872" />
<img width="1457" height="777" alt="image" src="https://github.com/user-attachments/assets/c190bc28-c100-4ce6-96f3-578885821530" />



</p>
<p>
On DC-1, open Server Manager, navigate to Add Roles and Features, and install the Active Directory Domain Services (AD DS) role to prepare the server for domain controller configuration.
</p>
<br />


<p>
<img width="1458" height="778" alt="image" src="https://github.com/user-attachments/assets/493091d2-1b6d-473a-8d53-27940d5a2472" />
<img width="1454" height="776" alt="image" src="https://github.com/user-attachments/assets/7f591c6b-014b-4609-bedf-2690c3ffc5bc" />
<img width="1459" height="777" alt="image" src="https://github.com/user-attachments/assets/49bd4fa8-f6a3-4879-b28b-3a97cf3183cc" />



</p>
<p>
After installing AD DS, launch the Domain Controller Configuration Wizard on DC-1. 
  
Choose Add a new forest and set the root domain to mydomain.com, then complete the promotion process to establish the domain.
</p>
<br />


<p>
<img width="450" height="543" alt="image" src="https://github.com/user-attachments/assets/0a72b3b9-2149-42fb-998e-0c25d0a3b435" />
<img width="1458" height="777" alt="image" src="https://github.com/user-attachments/assets/daf60054-33c7-4e2a-9e75-4831378c2d9e" />


</p>
<p>
After the server reboots, authenticate using the domain account (mydomain.com\labuser) and access Active Directory Users and Computers to begin administering the new domain environment.
</p>
<br />


<p>
<img width="1459" height="780" alt="image" src="https://github.com/user-attachments/assets/9ea51a15-cb4d-4758-a75b-53f53357954e" />
<img width="1456" height="778" alt="image" src="https://github.com/user-attachments/assets/a50e5c55-042a-467c-9456-82ac1e6bbc22" />
<img width="1459" height="778" alt="image" src="https://github.com/user-attachments/assets/b5442830-af48-478b-8bed-53389b0ea118" />



</p>
<p>
Within Active Directory Users and Computers, I created two Organizational Units: _EMPLOYEES to store regular user accounts and _ADMINS to contain elevated administrative accounts, establishing a structured domain hierarchy.
</p>
<br />


<p>
<img width="1460" height="779" alt="image" src="https://github.com/user-attachments/assets/8124d6a6-0ba9-48eb-9a83-debe56ba92b9" />
<img width="1456" height="781" alt="image" src="https://github.com/user-attachments/assets/b5ad9b36-c88a-4970-9943-82585387c641" />
<img width="1457" height="778" alt="image" src="https://github.com/user-attachments/assets/532ba46f-27e2-486e-b9a1-f621b2b48305" />
<img width="1457" height="781" alt="image" src="https://github.com/user-attachments/assets/88991743-e5ab-45d3-a2d3-62c57ce3f910" />
<img width="1456" height="777" alt="image" src="https://github.com/user-attachments/assets/8e421f19-078f-49ed-9671-36ef68d57a02" />
<img width="1457" height="778" alt="image" src="https://github.com/user-attachments/assets/20f8802b-cf5f-4249-951a-4938d407ff4d" />



</p>
<p>
Created a standard user account for Jane Doe and added the administrative account jane_admin to the Domain Admins security group to provision administrative access within the domain.
</p>
<br />


<p>
<img width="1456" height="777" alt="image" src="https://github.com/user-attachments/assets/c62eb5a7-00e6-4575-8235-f1f60a452b52" />
<img width="1458" height="780" alt="image" src="https://github.com/user-attachments/assets/6d3e74dd-35cc-4ca9-87c6-9fb1639ab641" />
<img width="1457" height="779" alt="image" src="https://github.com/user-attachments/assets/05913e7b-cd13-4c2d-b332-04fed6ee8ad5" />



</p>
<p>
Logged into Client-1 as the local administrator (labmaster) and joined the workstation to the domain using Settings → About → Rename this PC (Advanced) to integrate it into the Active Directory environment.
</p>
<br />


<p>
<img width="1455" height="777" alt="image" src="https://github.com/user-attachments/assets/1589bc47-65e8-4d74-ac4d-59d365f87cda" />
<img width="1456" height="776" alt="image" src="https://github.com/user-attachments/assets/61ea971d-9795-4d70-9245-629dd170065a" />
<img width="1456" height="778" alt="image" src="https://github.com/user-attachments/assets/38ac2d54-04bd-40bf-a5d2-ab369b257c33" />
<img width="1457" height="780" alt="image" src="https://github.com/user-attachments/assets/6f3954ef-bb9c-4092-8f28-17468e54e20a" />



</p>
<p>
On the Domain Controller, confirmed that Client-1 successfully joined the domain and appeared in the default Computers container. 
  
Then created an OU named _CLIENTS to structure workstation objects and moved Client-1 into the new OU for improved domain organization.
</p>
<br />



