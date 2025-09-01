# Network Access Control with Extended ACLs
使用擴展 ACL 實作網路存取控制

<h2>Outline 簡介</h2>

In this project, we implemented Extended Access Control Lists (ACLs) in Cisco Packet Tracer to precisely control network traffic between multiple hosts and a server. Two types of ACLs were configured and tested: Extended Numbered ACL and Extended Named ACL. These configurations demonstrate how network administrators can enforce policies based on source, destination, and specific services such as FTP, HTTP, and ICMP.

在本專題中，我們於 Cisco Packet Tracer 中實作 擴展存取控制清單 (ACL)，以精準控管多台主機與伺服器之間的網路流量。我們分別配置並測試了 編號式擴展 ACL 與 命名式擴展 ACL，展示了網路管理員如何根據來源、目的與特定服務 (如 FTP、HTTP、ICMP) 來制定網路存取政策。

---------

<h2>Key Learning Outcomes 主要學習成果</h2>

* Configure, apply, and verify an Extended Numbered ACL (設定、套用並驗證「編號式擴展 ACL」)

* Configure, apply, and verify an Extended Named ACL (設定、套用並驗證「命名式擴展 ACL」)

---------

<h2>Network Topology and Addressing Table 網路拓樸與位址表</h2>

<p align="center">
<b>Addressing Table (網路拓樸)</b><br/>
<img src="https://i.imgur.com/FwPJG4r.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<div align="center">
<b>Addressing Table (位址對照表)</b><br/>
  
| Device <br/>(設備) | Interface <br/>(介面) | IP Address <br/>(IP 位址) | Subnet Mask <br/>(子網路遮罩) | Default Gateway <br/>(預設閘道) |
| ----------------- | ---------------------- | -------------------------- | ----------------------------- | ------------------------------- |
| R1                | G0/0                   | 172.22.34.65               | 255.255.255.224               | N/A                             |
| R1                | G0/1                   | 172.22.34.97               | 255.255.255.240               | N/A                             |
| R1                | G0/2                   | 172.22.34.1                | 255.255.255.192               | N/A                             |
| Server            | NIC                    | 172.22.34.62               | 255.255.255.192               | 172.22.34.1                     |
| PC1               | NIC                    | 172.22.34.66               | 255.255.255.224               | 172.22.34.65                    |
| PC2               | NIC                    | 172.22.34.98               | 255.255.255.240               | 172.22.34.97                    |
</div>

---------

<h2>Materials and Methods 材料與方法</h2>

[Environment]
* Oracle VM VirtualBox (VirtualBox 虛擬機)</b>
* Kali Linux OS (Kali Linux 作業系統)</b>
* ClamAV antivirus suite (ClamAV 防毒套件)</b>

[Tasks]
* Configure Extended Numbered ACL (設定編號式擴展 ACL)</b>
* Apply ACL to Interface (套用 ACL 至介面)</b>
* Verify ACL through PC1 (透過 PC1 驗證 ACL)</b>
* Configure Extended Named ACL(設定命名式擴展 ACL)</b>
* Apply Named ACL to Interface (套用命名式 ACL 至介面)</b>
* Verify ACL through PC2 (透過 PC2 驗證 ACL)</b>

---------

<h2>Practice 實踐</h2>

<p align="center">
<b>Task 1: Install ClamAV<br/>(安裝 ClamAV)</b><br/>
<img src="https://i.imgur.com/eRoOvKQ.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Task 2: Update Virus Database<br/>(更新病毒碼) </b><br/>
<img src="https://i.imgur.com/a2Uo3iI.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Task 3: Download EICAR Test Virus<br/>(下載 EICAR 測試病毒) </b><br/>
<img src="https://i.imgur.com/7VMyOWI.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Task 4: Run ClamAV Scan<br/>(執行 ClamAV 掃描) </b><br/>
<img src="https://i.imgur.com/BHptf5x.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Task 5: Schedule Automatic Scans with Crontab使用 Crontab 設定排程掃描) </b><br/>
<img src="https://i.imgur.com/EJrT3da.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

---------

<h2>Results 成果展示</h2>

Through this lab, we successfully restricted network access according to different user requirements:<br/>透過本次實作，我們成功地依照不同使用者需求限制了網路存取：</b><br/>

* PC1 was allowed FTP and ICMP access to the server but denied communication with PC2.<br/>
  (PC1 可使用 FTP 與 ICMP 存取伺服器，但無法與 PC2 通訊)</b>
  <br/>
  
* PC2 was allowed HTTP and ICMP access to the server but denied FTP.<br/>
  (PC2 可使用 HTTP 與 ICMP 存取伺服器，但被禁止使用 FTP)</b>
  <br/>
  
* All other unspecified traffic was blocked by default due to the implicit deny any any rule.<br/>
  (由於預設的 deny any any 規則，所有未明確允許的流量皆被阻擋)</b>
  <br/>
  
This project reinforced key skills in network security and traffic control. The comparison between numbered and named ACLs highlighted that, while both achieve the same technical result, named ACLs provide better readability and maintainability, making them more suitable for real-world environments.

此專題強化了我們在網路安全與流量管控上的實務技能。比較編號式與命名式 ACL 的結果顯示：雖然兩者在技術上功能相同，但 命名式 ACL 在可讀性與維護性上更佳，因此在實際環境中更具優勢。


<h2>Reference 參考</h2>

[UniSQ] [CSC8520 - Securing Networks](https://handbook-guide.unisq.edu.au/course/2025/CSC8520)
<br/>
