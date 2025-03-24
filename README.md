<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Enterprise Network Configuration Project</title>
  <style>
    /* Global Styles */
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      line-height: 1.6;
      background-color: #f4f4f4;
      color: #333;
    }
    header, footer {
      background: #003366;
      color: #fff;
      padding: 20px 0;
      text-align: center;
    }
    header h1, footer p {
      margin: 0;
    }
    .container {
      width: 90%;
      max-width: 1100px;
      margin: 20px auto;
      background: #fff;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h2 {
      color: #003366;
      border-bottom: 2px solid #e0e0e0;
      padding-bottom: 5px;
    }
    .section {
      margin-bottom: 30px;
    }
    .image-container {
      text-align: center;
      margin: 20px 0;
    }
    .image-container img {
      max-width: 100%;
      height: auto;
      border: 2px solid #003366;
    }
    ul {
      list-style-type: disc;
      margin-left: 20px;
    }
    a {
      color: #003366;
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
    @media (max-width: 600px) {
      header, footer {
        padding: 15px 0;
      }
      .container {
        padding: 15px;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1>Enterprise Network Configuration Project</h1>
  </header>
  
  <div class="container">
    <!-- Overview Section -->
    <section class="section" id="overview">
      <h2>Overview</h2>
      <p>This project details a comprehensive enterprise network setup using VLAN segmentation and a multilayer core switch to manage inter-VLAN routing. It includes configurations for departmental access switches, a dedicated server-side switch, and extensive documentation for each component of the network.</p>
    </section>
    
    <!-- Network Architecture Section -->
    <section class="section" id="architecture">
      <h2>Network Architecture & Topology</h2>
      <p>The network is structured to ensure high performance, security, and scalability:</p>
      <ul>
        <li><strong>CoreSwitch:</strong> Serves as the multilayer switch enabling inter-VLAN routing and connecting all access and server switches via trunk links.</li>
        <li><strong>Department Access Switches:</strong> Dedicated switches for HR, CS, Marketing, IT, Management, and Finance departments, each configured with a unique VLAN.</li>
        <li><strong>ServerSwitch:</strong> Manages server resources by hosting VLANs for DHCP, Email, and HTTPS servers.</li>
      </ul>
      <div class="image-container">
        <!-- Replace 'images/View.png' with the actual image path in your repo -->
        <img src="images/View.png" alt="Network Topology Diagram">
      </div>
    </section>
    
    <!-- Configuration Details Section -->
    <section class="section" id="configurations">
      <h2>Configuration Details</h2>
      <p>The repository includes multiple configuration files and documentation that detail the commands and settings used across the network:</p>
      <ul>
        <li><strong>Configs_With_IPs.txt:</strong> Complete configuration for the CoreSwitch, Access Switches, and ServerSwitch with IP addressing details.</li>
        <li><strong>Configs.txt:</strong> Basic switch configuration file including welcome banners, VLAN setups, and trunk port settings.</li>
        <li><strong>Infa_Document_One.docx:</strong> Documentation covering the network topology, detailed configuration steps, and rationale behind the design.</li>
        <li><strong>Infa_Document_Two.docx:</strong> A comprehensive configuration guide, including command-by-command explanations and the overall network design.</li>
        <li><strong>MainInfa.pkt:</strong> The primary project file (Packet Tracer) containing the network simulation.</li>
      </ul>
    </section>
    
    <!-- How It Works Section -->
    <section class="section" id="how-it-works">
      <h2>How It Works</h2>
      <p>
        <strong>Inter-VLAN Routing:</strong> The CoreSwitch, with routing enabled and configured Switch Virtual Interfaces (SVIs), allows seamless communication between VLANs.
      </p>
      <p>
        <strong>VLAN Segmentation:</strong> Each department is isolated on its own VLAN, ensuring that network traffic remains organized and secure.
      </p>
      <p>
        <strong>Trunk Links:</strong> Trunk ports are used to connect the CoreSwitch with access switches, enabling the flow of multiple VLANs over a single link.
      </p>
      <p>
        <strong>Welcome Messages:</strong> Custom banners on each switch help identify devices and provide an initial layer of security.
      </p>
    </section>
    
    <!-- Project Files Structure Section -->
    <section class="section" id="files">
      <h2>Repository Structure</h2>
      <p>The repository is organized as follows:</p>
      <pre>
├── README.html         <!-- This file -->
├── css
│   └── styles.css      <!-- Optional external CSS -->
├── configs
│   ├── Configs_With_IPs.txt
│   ├── Configs.txt
├── docs
│   ├── Infa_Document_One.docx
│   └── Infa_Document_Two.docx
├── packettracer
│   └── MainInfa.pkt
└── images
    └── View.png       <!-- Network topology diagram -->
      </pre>
    </section>
    
    <!-- Conclusion Section -->
    <section class="section" id="conclusion">
      <h2>Conclusion</h2>
      <p>This project provides a scalable and secure enterprise network design. The use of VLAN segmentation, inter-VLAN routing via a multilayer switch, and comprehensive configuration documentation ensures that the network is both robust and easy to manage. For further details or to contribute, please refer to the project files and documentation.</p>
    </section>
  </div>
  
  <footer>
    <p>&copy; 2025 Enterprise Network Configuration Project</p>
  </footer>
</body>
</html>
