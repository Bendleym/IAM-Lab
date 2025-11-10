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
![OU Structure](<img width="764" height="541" alt="Capture2" src="https://github.com/user-attachments/assets/799d3271-db90-45cb-aa5b-0f21a554c2e3" />)

### 🖼️ User Examples  
![User Examples](<img width="742" height="538" alt="Capture3" src="https://github.com/user-attachments/assets/f8ebf3bc-58cd-4c96-acf9-633b681c2318" />)


### 🖼️ Domain Admin Membership  
![Domain Admin Membership](<img width="423" height="548" alt="Capture4" src="https://github.com/user-attachments/assets/184e5254-9780-4326-b240-29ae1932326c" />)

### 🖼️ PowerShell Privilege Audit  
![PowerShell Privilege Audit](<img width="966" height="516" alt="Capture6" src="https://github.com/user-attachments/assets/aa50ef6f-15a8-4335-838b-1e39411b0251" />0)


---

## 💻 GitHub Repo  
github.com/Bendleym/IAM-Lab  
📧 Bendleym@yahoo.com | LinkedIn: linkedin.com/in/bendley-milord
