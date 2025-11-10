# 🔐 IAM Privilege Audit & Automation Lab

## 🧩 Overview  
This lab simulates a real-world Identity and Access Management (IAM) environment using Active Directory and PowerShell.  
It shows how organizations audit privileges, enforce least privilege, and automate access reviews for compliance and security.  

---

## 🏗️ Environment Setup  
- Host: Windows Server 2022 (Domain Controller: DC01.lab.local)  
- Client: Windows 10 Pro (domain-joined workstation)  
- Tools Used: Active Directory Users & Computers, PowerShell, Group Policy  

---

## ⚙️ Configuration Process  
1. Installed Active Directory Domain Services and created a domain “lab.local.”  
2. Created Organizational Units: IT, HR, Finance, Admins, ServiceAccounts.  
3. Added sample users: John Doe, Jane Smith, Mark Lee, and Alice Admin.  
4. Placed users into their respective department OUs.  
5. Created security groups: IT_Group, HR_Group, Finance_Group, Admins_Group.  
6. Added Alice Admin to the Domain Admins group for privileged access.  

---

## 🔍 Privilege Audit Using PowerShell  
Commands used to validate IAM controls:  

```powershell
Get-ADUser -Filter * -Properties DistinguishedName | Select-Object Name, DistinguishedName
Get-ADGroupMember "Domain Admins" | Select-Object Name, SamAccountName, objectClass

Get-ADGroup -Filter * | ForEach-Object {
  Write-Host "`nGroup:" $_.Name -ForegroundColor Cyan
  Get-ADGroupMember $_.Name | Select-Object Name, SamAccountName
}
```

---

## 📊 Results  
Verified least-privilege access model.  
Confirmed only designated admin accounts had elevated rights.  
Demonstrated IAM auditing aligned with NIST 800-53 AC-2 and CIS Control 5.  

---

## 🧠 Takeaways  
Practiced identity provisioning and privilege auditing in AD.  
Automated access reviews with PowerShell.  
Strengthened understanding of IAM and least-privilege enforcement.  

---

## 📎 Screenshots  
### 🖼️ OU Structure  
![OU Structure](Capture2.PNG)

### 🖼️ User Examples  
![User Examples](Capture3.PNG)

### 🖼️ Domain Admin Membership  
![Domain Admin Membership](Capture4.PNG)

### 🖼️ PowerShell Privilege Audit  
![PowerShell Privilege Audit](Capture6.PNG) 

---

## 💻 GitHub Repo  
github.com/Bendleym/IAM-Lab  
📧 Bendleym@yahoo.com | LinkedIn: linkedin.com/in/bendley-milord
