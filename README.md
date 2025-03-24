<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Enterprise Network Configuration Project</title>
</head>
<body>
  <h1>Enterprise Network Configuration Project</h1>
  
  <h2>Overview</h2>
  <p>This project details a comprehensive enterprise network setup using VLAN segmentation and a multilayer core switch to manage inter-VLAN routing. It includes configurations for departmental access switches, a dedicated server-side switch, and extensive documentation for each component of the network.</p>
  
  <h2>Network Architecture & Topology</h2>
  <p>The network is structured to ensure high performance, security, and scalability:</p>
  <ul>
    <li><strong>CoreSwitch:</strong> Serves as the multilayer switch enabling inter-VLAN routing and connecting all access and server switches via trunk links.</li>
    <li><strong>Department Access Switches:</strong> Dedicated switches for HR, CS, Marketing, IT, Management, and Finance departments, each configured with a unique VLAN.</li>
    <li><strong>ServerSwitch:</strong> Manages server resources by hosting VLANs for DHCP, Email, and HTTPS servers.</li>
  </ul>
  <p><img src="images/View.png" alt="Network Topology Diagram" width="600"></p>
  
  <h2>Configuration Details</h2>
  <p>The repository includes multiple configuration files and documentation that detail the commands and settings used across the network:</p>
  <ul>
    <li><strong>Configs_With_IPs.txt:</strong> Complete configuration for the CoreSwitch, Access Switches, and ServerSwitch with IP addressing details.</li>
    <li><strong>Configs.txt:</strong> Basic switch configuration file including welcome banners, VLAN setups, and trunk port settings.</li>
    <li><strong>Infa_Document_One.docx:</strong> Documentation covering the network topology, detailed configuration steps, and rationale behind the design.</li>
    <li><strong>Infa_Document_Two.docx:</strong> A comprehensive configuration guide, including command-by-command explanations and the overall network design.</li>
    <li><strong>MainInfa.pkt:</strong> The primary project file (Packet Tracer) containing the network simulation.</li>
  </ul>
  
  <h2>How It Works</h2>
  <p><strong>Inter-VLAN Routing:</strong> The CoreSwitch, with routing enabled and configured Switch Virtual Interfaces (SVIs), allows seamless communication between VLANs.</p>
  <p><strong>VLAN Segmentation:</strong> Each department is isolated on its own VLAN, ensuring that network traffic remains organized and secure.</p>
  <p><strong>Trunk Links:</strong> Trunk ports are used to connect the CoreSwitch with access switches, enabling the flow of multiple VLANs over a single link.</p>
  <p><strong>Welcome Messages:</strong> Custom banners on each switch help identify devices and provide an initial layer of security.</p>
  
  <h2>Repository Structure</h2>
  <p>The repository is organized as follows:</p>
  <pre>
├── README.html         (This file)
├── configs
│   ├── Configs_With_IPs.txt
│   └── Configs.txt
├── docs
│   ├── Infa_Document_One.docx
│   └── Infa_Document_Two.docx
├── packettracer
│   └── MainInfa.pkt
└── images
    └── View.png       (Network topology diagram)
  </pre>
  
  <h2>Conclusion</h2>
  <p>This project provides a scalable and secure enterprise network design. The use of VLAN segmentation, inter-VLAN routing via a multilayer switch, and comprehensive configuration documentation ensures that the network is both robust and easy to manage. For further details or to contribute, please refer to the project files and documentation.</p>
  
  <p>&copy; 2025 Enterprise Network Configuration Project</p>
</body>
</html>
