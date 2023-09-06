# HoneyPotAzure
This project is a highly configurable honeypot that logs and tracks malicious access attempts to my Azure virtual machine. It visually maps these attempts on a real-time geographical map, providing a graphical representation of ongoing security threats.
![image](https://github.com/GussBad/HoneyPotAzure/assets/98527927/00c9858f-79a6-4fb2-8441-36a696dfe4bf)


## Key Features

- Real-Time Monitoring: Track and visualize malicious access attempts to your virtual machine in real-time.
- Geographical Tracking: Map the origin of access attempts on an interactive map.
- Flexible Configuration: Customize honeypot settings to suit your specific security needs.
- Alerts and Notifications: Receive alerts and notifications when suspicious activities are detected.


## How It Works

1. Azure Virtual Machine Setup
Initially, we provisioned a virtual machine on Microsoft Azure to serve as a honeypot (a deliberately vulnerable machine).
2. Enabling Echo Requests
We configured the virtual machine to accept ICMP Echo (ping) requests to create a target for potential unauthorized access attempts.
3. IP Geolocation API Integration
We utilized the IP geolocation API provided by ipgeolocation.io to obtain detailed information about the IP addresses attempting to access the virtual machine.
4. PowerShell Data Retrieval
We created a PowerShell script that periodically checks access logs and collects data, including IP addresses, timestamps, and any other relevant information.

![Script da virtual machine](https://github.com/GussBad/HoneyPotAzure/assets/98527927/b3a5179d-ab18-4a44-871d-69f3fadd9f0b)


6. Logging to Text File
The data collected by PowerShell is logged into a text file located on the virtual machine.
7. Data Transfer to Server
We configured the virtual machine to periodically send access log data from the text file to a remote server.

9. Server-Side Processing
On the server, we set up an environment to process the data received from access logs. We used Custom Log functionality to interpret and categorize the data based on criteria such as country, city, and state.

![ScriptServerSide](https://github.com/GussBad/HoneyPotAzure/assets/98527927/b8ad56b9-d1d1-4521-b337-8430c7962afb)



10. Geolocation and Mapping
With categorized data, we enabled a mapping feature that uses latitude and longitude coordinates to plot the origins of access attempts on an interactive map. This allows us to visually track the geolocation of attacks.


  ![Map Script](https://github.com/GussBad/HoneyPotAzure/assets/98527927/4c5fe984-9e8e-486c-a558-d6370469eb1c)

