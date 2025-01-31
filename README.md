<p align="center">
<img src="https://i.imgur.com/Aja9D5E.jpeg" />
</p>

<h1>VirtualBox - Multi-VM Networking</h1>
Networking multiple virtual machines in VirtualBox allows for efficient file transfers, hardware redundancy, and the creation of scalable networks for testing and communication. This guide walks you through setting up a host-only network in VirtualBox. <br />

<h2>Environments and Technologies Used</h2>

- VirtualBox  
- VirtualBox Extension Pack  
- Ubuntu  

<h2>Operating System Used</h2>

- Linux (Ubuntu and CentOS)  

<h2>Prerequisites</h2>

- VMs with 2GB of RAM minimum (4GB recommended)  
- Multicore processor  
- Sufficient hard drive space (varies based on virtual machine usage)  

<h2>Configuring VirtualBox Networking</h2>


<p>
<img src="https://i.imgur.com/CaK4ExB.png" />
</p>
<p>
The host network needs to be configured. Open VirtualBox, click **Tools**, and select **Host-only Networks**. Configure the settings as desired. Ensure the **DHCP Server** option is enabled to allow VirtualBox to automatically assign IP addresses.
</p>

<p>
<img src="https://i.imgur.com/DCVpodm.png" />
</p>
<p>
Select the first virtual machine you want to add to the network. Click **Settings**, then navigate to the **Network** tab. Under **Adapter 1**, check **Enable Network Adapter**. Choose the desired network configuration. In this case, attach your Ubuntu VM to the **Host-only Adapter** (e.g., VirtualBox Host-Only Ethernet Adapter). Repeat this process for all your VMs to ensure they are on the same network.
</p>

<h2>Verify Network Connectivity</h2>

<p>
<img src="https://i.imgur.com/1qgXnok.png" />
</p>
<p>
<img src="https://i.imgur.com/yvXBUaA.png" />
</p>
<p>
After configuring the networking, start the virtual machines to verify connectivity. Open a terminal and use tools like `ping` or `curl`. For Ubuntu, `ping` works out of the box. For CentOS, you may need to install additional packages to use `curl`. If DHCP is enabled, use `ifconfig` or `ip addr` to find the VM's IP address. Test connectivity by running `ping <IP address>` to communicate with another VM in the network.
</p>

<h2>Testing Network Connectivity</h2>

<p>
<img src="https://i.imgur.com/P3Rlu7a.png" />
</p>
<p>
<img src="https://i.imgur.com/dhhDA9f.png" />
</p>
<p>
From the host VM, use the `ping` command to check connectivity with VM2 using its IP address (e.g., `ping 192.168.56.102`). Similarly, from VM2, ping the host VM (e.g., `ping 192.168.56.101`). Ensure both VMs can communicate with each other.
</p>

<h3>Common Troubleshooting Issues</h3>
<ul>
  <li>Ensure the correct network adapter is selected in the **Network** settings.</li>
  <li>Verify the VM's network interface is enabled and has a valid IP address.</li>
  <li>Restart the VMs or VirtualBox if changes are not reflected.</li>
</ul>
