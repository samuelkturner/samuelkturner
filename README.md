<h1>Hi, I'm Sam! Passionate Cybersecurity Analyst</h1>

<h2>👨‍💻 Cybersecurity Projects:</h2>

- <b>Azure / Cloud Projects</b>
  - [Creating a Live SOC/Honeynet in Azure](https://github.com/samuelkturner/azure-net)

<h2> 🤳 Connect with me:</h2>

[<img align="left" alt="JoshMadakor | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />][linkedin]
[<img align="left" alt="JoshMadakor | Instagram" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/instagram.svg" />][instagram]

[instagram]: https://www.instagram.com/joshmadakor/
[linkedin]: https://linkedin.com/in/joshmadakor

<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AD Lab Architecture Diagram</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&family=Inter:wght@300;400;600&display=swap');

- { margin: 0; padding: 0; box-sizing: border-box; }

body {
background: #0a0e1a;
display: flex;
justify-content: center;
align-items: center;
min-height: 100vh;
font-family: ‘Inter’, sans-serif;
padding: 40px 20px;
}

.diagram-wrapper {
width: 100%;
max-width: 1000px;
}

.title-block {
text-align: center;
margin-bottom: 32px;
}

.title-block h1 {
font-family: ‘JetBrains Mono’, monospace;
font-size: 18px;
color: #00d4ff;
letter-spacing: 2px;
text-transform: uppercase;
margin-bottom: 6px;
}

.title-block p {
color: #4a5568;
font-size: 13px;
font-family: ‘JetBrains Mono’, monospace;
}

.azure-cloud {
background: linear-gradient(135deg, #0d1b2e 0%, #0a1628 100%);
border: 1.5px solid #1e3a5f;
border-radius: 16px;
padding: 32px;
position: relative;
box-shadow: 0 0 60px rgba(0, 120, 212, 0.1), inset 0 0 60px rgba(0,0,0,0.3);
}

.azure-label {
position: absolute;
top: -13px;
left: 24px;
background: #0078d4;
color: white;
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
font-weight: 700;
letter-spacing: 1.5px;
padding: 3px 12px;
border-radius: 4px;
text-transform: uppercase;
}

.vnets-row {
display: flex;
gap: 24px;
align-items: stretch;
position: relative;
}

.vnet {
flex: 1;
border-radius: 12px;
padding: 20px;
position: relative;
}

.vnet-dc {
background: rgba(0, 120, 212, 0.06);
border: 1.5px solid rgba(0, 120, 212, 0.4);
}

.vnet-client {
background: rgba(0, 188, 140, 0.06);
border: 1.5px solid rgba(0, 188, 140, 0.4);
}

.vnet-label {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
font-weight: 700;
letter-spacing: 1px;
text-transform: uppercase;
margin-bottom: 4px;
}

.vnet-dc .vnet-label { color: #0078d4; }
.vnet-client .vnet-label { color: #00bc8c; }

.vnet-subnet {
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
color: #4a5568;
margin-bottom: 16px;
}

.vm-card {
background: #0d1b2e;
border-radius: 10px;
padding: 16px;
border: 1px solid rgba(255,255,255,0.08);
position: relative;
}

.vm-header {
display: flex;
align-items: center;
gap: 10px;
margin-bottom: 12px;
}

.vm-icon {
width: 32px;
height: 32px;
border-radius: 6px;
display: flex;
align-items: center;
justify-content: center;
font-size: 16px;
flex-shrink: 0;
}

.vm-icon-dc { background: rgba(0, 120, 212, 0.2); }
.vm-icon-client { background: rgba(0, 188, 140, 0.2); }

.vm-name {
font-family: ‘JetBrains Mono’, monospace;
font-size: 14px;
font-weight: 700;
color: #e2e8f0;
}

.vm-os {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: #4a5568;
margin-top: 2px;
}

.vm-ip {
display: inline-block;
background: rgba(255,255,255,0.05);
border: 1px solid rgba(255,255,255,0.1);
border-radius: 4px;
padding: 3px 8px;
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
color: #00d4ff;
margin-bottom: 12px;
}

.service-list {
list-style: none;
}

.service-list li {
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
color: #718096;
padding: 3px 0;
display: flex;
align-items: center;
gap: 6px;
}

.service-list li::before {
content: ‘▸’;
font-size: 10px;
}

.vnet-dc .service-list li::before { color: #0078d4; }
.vnet-client .service-list li::before { color: #00bc8c; }

.peering-bridge {
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
width: 100px;
flex-shrink: 0;
gap: 8px;
}

.peering-line {
width: 2px;
flex: 1;
background: linear-gradient(to bottom, transparent, #f59e0b, #f59e0b, transparent);
position: relative;
}

.peering-badge {
background: rgba(245, 158, 11, 0.15);
border: 1px solid rgba(245, 158, 11, 0.5);
border-radius: 6px;
padding: 6px 10px;
text-align: center;
white-space: nowrap;
}

.peering-badge .badge-label {
font-family: ‘JetBrains Mono’, monospace;
font-size: 9px;
font-weight: 700;
color: #f59e0b;
letter-spacing: 1px;
text-transform: uppercase;
display: block;
}

.peering-arrow {
color: #f59e0b;
font-size: 16px;
line-height: 1;
}

.bottom-row {
display: flex;
gap: 16px;
margin-top: 24px;
}

.info-card {
flex: 1;
background: rgba(255,255,255,0.03);
border: 1px solid rgba(255,255,255,0.07);
border-radius: 8px;
padding: 14px;
}

.info-card-title {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
font-weight: 700;
letter-spacing: 1.5px;
text-transform: uppercase;
margin-bottom: 8px;
color: #4a5568;
}

.event-row {
display: flex;
align-items: center;
gap: 8px;
padding: 3px 0;
}

.event-id {
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
font-weight: 700;
color: #f59e0b;
min-width: 40px;
}

.event-desc {
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: #4a5568;
}

.user-pill {
display: inline-flex;
align-items: center;
gap: 5px;
background: rgba(255,255,255,0.04);
border: 1px solid rgba(255,255,255,0.08);
border-radius: 20px;
padding: 4px 10px;
margin: 3px 2px;
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
color: #718096;
}

.user-dot {
width: 7px;
height: 7px;
border-radius: 50%;
background: #00bc8c;
}

.nsg-badge {
display: inline-flex;
align-items: center;
gap: 5px;
background: rgba(239, 68, 68, 0.1);
border: 1px solid rgba(239, 68, 68, 0.3);
border-radius: 4px;
padding: 3px 8px;
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: #ef4444;
margin: 3px 2px;
}

.port-badge {
display: inline-flex;
align-items: center;
background: rgba(0, 120, 212, 0.1);
border: 1px solid rgba(0, 120, 212, 0.3);
border-radius: 4px;
padding: 3px 8px;
font-family: ‘JetBrains Mono’, monospace;
font-size: 10px;
color: #0078d4;
margin: 3px 2px;
}

.domain-badge {
display: inline-block;
background: rgba(139, 92, 246, 0.1);
border: 1px solid rgba(139, 92, 246, 0.3);
border-radius: 4px;
padding: 3px 10px;
font-family: ‘JetBrains Mono’, monospace;
font-size: 11px;
color: #8b5cf6;
margin-bottom: 10px;
}
</style>

</head>
<body>
<div class="diagram-wrapper">
<div class="title-block">
<h1>Cloud-Based Active Directory Lab</h1>
<p>Microsoft Azure // Windows Server 2025 // corp.local Domain</p>
</div>

<div class="azure-cloud">
<div class="azure-label">☁ Microsoft Azure</div>

```
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
```

</div>
</div>
</body>
</html>
