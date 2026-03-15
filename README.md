<h1>Hi, I'm Sam! Passionate Cybersecurity Analyst</h1>

<h2>👨‍💻 Cybersecurity Projects:</h2>

- <b>Azure / Cloud Projects</b>
  - [Creating a Live SOC/Honeynet in Azure](https://github.com/samuelkturner/azure-net)

<h2> 🤳 Connect with me:</h2>

[<img align="left" alt="JoshMadakor | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />][linkedin]
[<img align="left" alt="JoshMadakor | Instagram" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/instagram.svg" />][instagram]

[instagram]: https://www.instagram.com/samuelkturner/
[linkedin]: https://linkedin.com/in/samuelkturner/

<div style="text-align:center; margin-bottom: 20px;">
<div class="domain-badge">🏢 Domain: corp.local</div>
</div>

<div class="vnets-row">
<!-- DC01 VNet -->
<div class="vnet vnet-dc">
<div class="vnet-label">vnet-westus-2</div>
<div class="vnet-subnet">172.18.0.0/24 • West US</div>
<div class="vm-card">
<div class="vm-header">
<div class="vm-icon vm-icon-dc">🖥️</div>
<div>
<div class="vm-name">DC01</div>
<div class="vm-os">Windows Server 2025</div>
</div>
</div>
<div class="vm-ip">Private IP: 172.18.0.4</div>
<ul class="service-list">
<li>Active Directory Domain Services</li>
<li>DNS Server (corp.local zones)</li>
<li>Domain Controller</li>
<li>Event Viewer Security Logs</li>
<li>ADUC — TestUsers OU</li>
</ul>
</div>
</div>

<!-- Peering Bridge -->
<div class="peering-bridge">
<div class="peering-line"></div>
<div class="peering-badge">
<span class="badge-label">VNet</span>
<span class="badge-label">Peering</span>
</div>
<div class="peering-arrow">⇄</div>
<div class="peering-line"></div>
</div>

<!-- CLIENT01 VNet -->
<div class="vnet vnet-client">
<div class="vnet-label">AD-VNet</div>
<div class="vnet-subnet">10.0.0.0/24 • West US</div>
<div class="vm-card">
<div class="vm-header">
<div class="vm-icon vm-icon-client">💻</div>
<div>
<div class="vm-name">CLIENT01</div>
<div class="vm-os">Windows Server 2025</div>
</div>
</div>
<div class="vm-ip">Private IP: 10.0.0.4</div>
<ul class="service-list">
<li>Domain Member (corp.local)</li>
<li>DNS → 172.18.0.4 (DC01)</li>
<li>RDP Port 3389 (NSG rule)</li>
<li>Remote Desktop Users: Alice</li>
<li>Domain Auth Verified</li>
</ul>
</div>
</div>
</div>

<!-- Bottom Info Row -->
<div class="bottom-row">

<!-- Domain Users -->
<div class="info-card">
<div class="info-card-title">👥 Domain Users (TestUsers OU)</div>
<div>
<span class="user-pill"><div class="user-dot"></div>corp\alice</span>
<span class="user-pill"><div class="user-dot"></div>corp\bob</span>
<span class="user-pill"><div class="user-dot"></div>corp\charlie</span>
</div>
</div>

<!-- Security Events -->
<div class="info-card">
<div class="info-card-title">🔍 Monitored Event IDs</div>
<div class="event-row"><span class="event-id">4624</span><span class="event-desc">Successful Logon</span></div>
<div class="event-row"><span class="event-id">4625</span><span class="event-desc">Failed Logon</span></div>
<div class="event-row"><span class="event-id">4720</span><span class="event-desc">User Account Created</span></div>
</div>

<!-- NSG / Ports -->
<div class="info-card">
<div class="info-card-title">🔒 Network Security</div>
<div>
<span class="nsg-badge">NSG Rules</span>
<span class="port-badge">RDP :3389</span>
<span class="port-badge">DNS :53</span>
<span class="port-badge">LDAP :389</span>
</div>
</div>

</div>
