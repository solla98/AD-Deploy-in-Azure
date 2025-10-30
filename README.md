<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

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
