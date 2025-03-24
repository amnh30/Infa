<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Enterprise Network Configuration Project</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px;
      line-height: 1.6;
      background-color: #f7f7f7;
      color: #333;
    }
    header, footer {
      text-align: center;
      padding: 10px;
      background-color: #004080;
      color: #fff;
    }
    h1, h2, h3 {
      color: #004080;
    }
    section {
      background: #fff;
      padding: 20px;
      margin-bottom: 20px;
      border-radius: 5px;
      box-shadow: 0 0 5px rgba(0,0,0,0.1);
    }
    .screenshot {
      text-align: center;
      margin: 20px 0;
    }
    .screenshot img {
      max-width: 100%;
      height: auto;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    pre {
      background: #e8e8e8;
      padding: 15px;
      overflow: auto;
      border-radius: 4px;
      font-size: 0.9em;
    }
    a {
      color: #004080;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <header>
    <h1>Enterprise Network Configuration Project</h1>
  </header>

  <section id="overview">
    <h2>Overview</h2>
    <p>This project sets up a segmented enterprise network. The configuration uses a multilayer (core) switch for inter-VLAN routing and multiple departmental access switches to ensure traffic isolation and efficient management. A dedicated server-side switch hosts key server resources. The configuration files include VLAN creation, interface settings, and security banners for each device.</p>
  </section>

  <section id="topology">
    <h2>Network Topology & Components</h2>
    <ul>
      <li><strong>Core (Multilayer) Switch:</strong> Acts as the central hub performing inter-VLAN routing and connects to all departmental and server switches using trunk links.</li>
      <li><strong>Department Access Switches:</strong> Separate switches for HR, CS, Marketing, IT, Management, and Finance, each assigned its own VLAN.</li>
      <li><strong>Server-Side Switch:</strong> Connects servers such as DHCP, Email, and HTTPS with dedicated VLANs.</li>
    </ul>
    <div class="screenshot">
      <img src="Capture.JPG" alt="Network Diagram">
      <p><em>Figure: Network Diagram Overview</em></p>
    </div>
  </section>

  <section id="configuration">
    <h2>Detailed Configuration</h2>
    
    <h3>Core Switch (CoreSwitch)</h3>
    <p>The CoreSwitch is configured with the following features:</p>
    <ul>
      <li><strong>Hostname & Banner:</strong> Custom welcome message for authorized access.</li>
      <li><strong>Inter-VLAN Routing:</strong> Enabled with IP routing and configured SVIs for each VLAN.</li>
      <li><strong>VLANs:</strong> Includes departmental VLANs (10 to 60) and server VLANs (100, 110, 120).</li>
      <li><strong>Trunk Ports:</strong> Two trunk ports (GigabitEthernet0/1 and 0/2) allow traffic for all VLANs.</li>
    </ul>
    <pre>
! CoreSwitch Configuration Sample
hostname CoreSwitch
banner motd #
  ********************************************
  *  Welcome to the Core (Multilayer) Switch  *
  *       Authorized Personnel Only!         *
  ********************************************
ip routing
vlan 10
 name HR
...
interface GigabitEthernet0/1
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30,40,50,60,100,110,120
write memory
    </pre>

    <h3>Department Access Switches</h3>
    <p>Each departmental switch (e.g., HR_Switch, CS_Switch, etc.) is configured to:</p>
    <ul>
      <li>Display a department-specific welcome banner.</li>
      <li>Create and assign the appropriate VLAN (e.g., VLAN 10 for HR, VLAN 20 for CS).</li>
      <li>Configure access ports for end-user devices and a trunk uplink port to the CoreSwitch.</li>
    </ul>
    <pre>
! HR_Switch Configuration Sample
hostname HR_Switch
banner motd #
  ************************************
  *   Welcome to the HR Department   *
  *       Access Switch              *
  ************************************
vlan 10
 name HR
interface range FastEthernet0/1-12
 switchport mode access
 switchport access vlan 10
interface GigabitEthernet0/1
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30,40,50,60
write memory
    </pre>

    <h3>Server-Side Switch (ServerSwitch)</h3>
    <p>The ServerSwitch hosts server resources with the following configuration:</p>
    <ul>
      <li><strong>Hostname & Banner:</strong> Custom welcome message for the server room.</li>
      <li><strong>VLANs for Servers:</strong> Includes VLANs for DHCP (100), Email (110), and HTTPS (120).</li>
      <li><strong>Trunk Port:</strong> Configured to carry both departmental and server VLANs.</li>
    </ul>
    <pre>
! ServerSwitch Configuration Sample
hostname ServerSwitch
banner motd #
  ********************************************
  *  Welcome to the Server Room Switch       *
  *       Authorized Personnel Only!         *
  ********************************************
vlan 100
 name DHCP_Server
vlan 110
 name Email_Server
vlan 120
 name HTTPS_Server
interface GigabitEthernet0/1
 switchport mode trunk
 switchport trunk allowed vlan 100,110,120,10,20,30,40,50,60
write memory
    </pre>
  </section>

  <section id="documentation">
    <h2>Project Documentation</h2>
    <p>The complete network documentation details the rationale behind each configuration step:</p>
    <ul>
      <li><strong>Overview Documents:</strong> Provide project scope, objectives, and network segmentation.</li>
      <li><strong>Configuration Files:</strong> Contain all commands for VLAN creation, interface configuration, and security settings.</li>
      <li><strong>Verification Commands:</strong> Used to confirm VLAN assignments, trunk settings, and routing tables.</li>
    </ul>
    <p>Refer to the configuration documents for more details on the setup and to guide future modifications or troubleshooting.</p>
  </section>

  <footer>
    <p>&copy; 2025 Enterprise Network Configuration Project</p>
  </footer>
</body>
</html>
