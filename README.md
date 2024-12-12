# Active_Directory
Setting up an Active Directory environment using Windows Server 2022 and Windows 10 Pro.

<h2>Purpose</h2>
The purpose of this lab is to learn how to configure a server to administer multiple groups made up of many users. After successfully configuring the server, the goal is to create policies that apply to specific roles. These roles could range from administration permissions to deparment based policies.
Overall, by completing this lab (and having just the general curiosity to poke around), one should have a better grasp of how Active Directory works at a very fundamental level.

<h2>Steps:</h2>
<h3>Install Oracle Virtual Box</h3>
<li>Head over to Oracle Virtual Box's website and download the application</li>
 <a href=https://www.virtualbox.org/>here.</a>
<h3>Download Windows 10 and Windows Server 2022 ISO</h3>
An ISO file is similar to having the physical disc that helps install the OS. This will help us get to the installation process for both Windows 10 and Windows Server 2022 without the need for a disc reader. 
<br>
<ol>
    <li>Download the multi-edition Windows 10 graphical ISO from Microsoft's website.</li>
    <li>Download the Windows Server 2022 from the Microsoft Evaulation Center. (looking for the ISO, not the virtual machine in Azure)</li>  
</ol>
<h3>Spin Up Two VMs</h3>
<h4>Windows 10 Pro</h4>
<ol>
  <li>Open Virtual Box and click "New" to create a new virtual machine.</li>
  <li>Give the VM a name, a file path to save the data, and select the Windows 10 ISO as the "intended installation".</li>
  <li>Click the "Skip Unattended Installation" checkbox and move on to the next page</li>
  <li>Provision the appropriate hardware resources like RAM and CPU cores for the VM. I chose 4096 MB of RAM and 3 CPU cores.</li>
  <li>Click "Next" on all the prompts until reaching the "Finish" button.</li>
  <li>Once installation is complete, click "Next" then "Install Now"</li>
  <li>At the bottom of the window select "I don't have a product key"</li>
  <li>Then proceed to selecting the specific OS that we need for this project which is "Windows 10 Pro"</li>
  <li>Accept the license terms and create a "Custom" install.</li>
  <li>Click "Next" and Windows will begin installing.</li>
</ol>
<h4>Windows Server 2022</h4>
    While Windows 10 Pro is installing, repeat steps 1-6 for Windows Server 2022 from the Windows 10 Pro section
<ol>
 <li>For the specific OS that we want to install, it should be the "Standard Evalutation (Desktop Experience)" since we want to be able to view our environment with a GUI or graphical user interface.</li>
 <li>Accept Microsoft's License terms and select "Custom" for the type of installation.</li>
 <li>Click "Next" and Windows Server will begin installing</li>
</ol>
<strong><em>At this point it is important that we go back to the Oracle Virtual Box application and change the Network settings for both VMs from NAT to NAT network, so that they can communicate with each other.</em></strong>


<h3>Configure AD Domain Services</h3>
The very first thing to do inside the Windows Server VM is to set up Active Directory Domain Services.
<ol>
 <li>Open the Server Manager application. It should automatically open on startup.</li>
 <li>On the top ribbon of buttons, click on the "Manage" button and navigate to "Add Roles and Features".</li>
 <li>Click "Next", until you get to the "Server Roles" page and click the "Active Directory Domain Services" checkbox.</li>
 <li>Continue clicking "Next" until the "Install" button is no longer grey and can be clicked and install the features!</li>
 <li>On the Server Manager dashboard, there will now be an icon that looks like a flag with an exclamation point within a yellow triangle next to the "Manage" button we used earlier. Click that as well as the blue underlined text "Promote this server to a domain controller"</li>
 <li>Click "Add a new forest" and add a Root domain name. Name whatever you like but add ".local" to the end.</li>
 <li>Create a secure password for the server and continue to hit "Next" until the "Install" button is no longer grey.</li>
 <li>The server will sign out the user and start applying the new features.</li>
</ol>
<h4>Set Static IP</h4>
Now it's time to set the static IP address for the server so that it is not randomly assigned an IP from DHCP.
<ol>
 <li>On the right of the taskbar, click on the "No Internet" symbol marked via a globe with a grid inside.</li>
 <li>Left-click again on the only connection that should show up. This should open the Ethernet settings page.</li>
 <li>Head to the "Related settings" subheading and click the first option "Change adapter options"</li>
 <li>Here we will see our network connection. Right-click this and open the "Properties" tab</li>
 <li>Out of the list of Ethernet Properties we are looking for the IPv4. Double click to open this setting.</li>
 <li>Now we will be able to set our static IP to something that isn't being used on the network already (since this is one of two VMs right now we don't have to worry about using the same one as others as much; use ipconfig in a terminal to see what the dynamically assigned IP is).</li>
 <li>Enter a subnet mask. (ex. 255.255.255.0)</li>
 <li>Enter the gateway. (use ipconfig in any terminal to find this)</li>
 <li>For the DNS settings we can keep the loopback addres of 127.0.0.1 but we can add Google's DNS as a secondary server which is 8.8.8.8</li>
 <li>Now we should be connected to the network. Ping the default gateway and google.com to verify that everything is working.</li>
</ol>

<h4>Create Groups & Users</h4>
<h4>Create Group Policies</h4>
<h3>Configure Workstation for AD</h3>
<ol>
  <li>Customize Windows to the language and keyboard layout you prefer.</li>
</ol>
<h4>Update DNS Config</h4>
<h4>Add Workstation to Domain</h4>
<h4>Test Group Policies</h4>

<h2>Takeaways</h2>
By the end of this lab one should be able to:<br>
- Configure a server with Active Directory <br>
- Create different Organizational Units (Groups) and Users<br>
- Configure OUs and users with different group policies<br>
- Set a static IP and DNS server<br>
<br>
Can be learned intuitively:<br>
- Password reset<br>
- Account disable<br>
