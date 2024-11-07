# azure-network-protocols

<h2>Environments and Technologies Used</h2>
<ul>
    <li>Microsoft Azure (Virtual Machines/Compute)</li>
    <li>Remote Desktop</li>
    <li>Various Command-Line Tools</li>
    <li>Various Network Protocols (SSH, RDP, DNS, HTTP/S, ICMP)</li>
    <li>Wireshark (Protocol Analyzer)</li>
</ul>

<h2>Operating Systems Used</h2>
<ul>
    <li>Windows 10 (21H2)</li>
    <li>Ubuntu Server 20.04</li>
</ul>

<h2>High-Level Steps</h2>
<ul>
    <li>Step 1: Set up Azure Virtual Machines and NSGs</li>
    <li>Step 2: Configure Traffic Flow and Capture with Wireshark</li>
    <li>Step 3: Analyze Traffic Using Wireshark</li>
    <li>Step 4: Modify NSG Rules and Observe Traffic Changes</li>
</ul>

<h2>Actions and Observations</h2>

<h3>1. Set up Azure Virtual Machines and NSGs</h3>
<p>In the first step, deploy two or more Virtual Machines (VMs) within Azure. Configure the Virtual Machines using the necessary operating systems (Windows 10, Ubuntu Server, etc.). Additionally, create and configure a Network Security Group (NSG) to manage inbound and outbound traffic to and from the VMs.</p>
<ul>
    <li>Go to the Azure portal and deploy VMs with the required operating systems.</li>
    <li>Ensure each VM has a private IP address and is connected to the same Virtual Network (VNet) for communication.</li>
    <li>Create a Network Security Group (NSG) to define traffic rules and assign it to the network interface or subnet of the VMs.</li>
</ul>

<h3>2. Configure Traffic Flow and Capture with Wireshark</h3>
<p>Once your VMs are set up and connected, it's time to configure network traffic flow and capture it using Wireshark.</p>
<ul>
    <li>Install Wireshark on a machine that has network access to the VMs, or install it on one of the VMs themselves.</li>
    <li>Use Wireshark to start capturing network traffic. Filter the captured traffic by protocol (e.g., ICMP for pings, TCP for SSH/RDP, etc.) to focus on specific types of communication.</li>
    <li>Generate network traffic between the VMs, such as pinging the VMs, establishing RDP/SSH connections, or accessing web services hosted on the VMs.</li>
</ul>

<h3>3. Analyze Traffic Using Wireshark</h3>
<p>With traffic being captured, use Wireshark's powerful analysis tools to review the network packets. Here’s how to proceed:</p>
<ul>
    <li>Examine the traffic logs to identify the communication between VMs. Look at the source and destination IP addresses, ports, and protocols used.</li>
    <li>Use filters in Wireshark to narrow down the captured traffic. For example, filter by “icmp” to analyze ping requests or by “tcp.port==80” to view HTTP traffic.</li>
    <li>Observe any unexpected or unauthorized traffic that might be happening between the VMs.</li>
</ul>

<h3>4. Modify NSG Rules and Observe Traffic Changes</h3>
<p>Now, experiment with modifying the NSG rules to control and filter the traffic between the VMs. This will allow you to see how the rules you apply affect the flow of network traffic.</p>
<ul>
    <li>In the Azure portal, go to the Network Security Group you created and modify the inbound and outbound security rules. For example, you can deny ICMP traffic to block ping requests or allow only specific IPs or subnets to access the VMs.</li>
    <li>After modifying the NSG rules, return to Wireshark and observe how the traffic flow changes. Ensure that only allowed traffic is flowing between the VMs and that blocked traffic is being filtered as expected.</li>
    <li>Test various scenarios, such as blocking access to certain ports or denying traffic from certain IP addresses, and analyze how this impacts the network traffic.</li>
</ul>

