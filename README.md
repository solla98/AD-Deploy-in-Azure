<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

# On-premises Active Directory Deployed in the Cloud (Azure)

This tutorial outlines the implementation of an on-premises Active Directory environment using Azure Virtual Machines.

---

## Environments and Technologies Used
- Microsoft Azure (Virtual Machines / Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

---

## Operating Systems Used
- Windows Server 2022
- Windows 10

---

## Table of Contents
- [Setting up Active Directory in Azure](#setting-up-active-directory-in-azure)
- [Deploy Active Directory Steps](#deploy-active-directory-steps)

<br/>

## Setting up Active Directory in Azure

<p>
<img width="1455" height="780" alt="image" src="https://github.com/user-attachments/assets/2ece5062-3d2b-4c84-b3ff-353022981cd4" />
<img width="1453" height="780" alt="image" src="https://github.com/user-attachments/assets/bf186555-524b-480d-94f4-7058ecc5a480" />
<img width="1453" height="778" alt="image" src="https://github.com/user-attachments/assets/2a06bd3c-e708-4754-890b-772562944e1c" />
</p>

Change the private IP address on DC-1 from dynamic to static to ensure consistent network identification.

Set Client-1’s DNS server to the private IP of DC-1.

Log into Client-1 and verify connectivity to DC-1 via ping and DNS resolution (`ipconfig /all`).

Compare DNS configuration on DC-1 with Client-1 to ensure proper settings.

---

## Deploy Active Directory Steps

<p>
<img width="1456" height="777" alt="image" src="https://github.com/user-attachments/assets/2b17b26f-a3ef-4ffa-935c-32641817d355" />
</p>

On DC-1, open Server Manager, navigate to Add Roles and Features, and install the Active Directory Domain Services (AD DS) role.

Promote DC-1 to a domain controller and create a new forest: **mydomain.com**.

After the server reboots, log in as **mydomain.com\labuser** and open **Active Directory Users and Computers**.

Create Organizational Units: `_EMPLOYEES` and `_ADMINS`.

Create a user account for Jane Doe and add `jane_admin` to the **Domain Admins** group.

Log into Client-1 as the local administrator and join the machine to the domain.

Create an OU `_CLIENTS` and move Client-1 into it.
