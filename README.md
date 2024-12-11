# Active_Directory
Setting up an Active Directory environment using Windows Server 2022 and Windows 10 Pro.

<h2>Purpose</h2>
The purpose of this lab is to learn how to configure a server to administer multiple groups made up of many users. After successfully configuring the server, the goal is to create policies that apply to specific roles. These roles could range from administration permissions to deparment based policies.
Overall, by completing this lab (and having just the general curiosity to poke around), one should have a better grasp of how Active Directory works at a very fundamental level.

<h2>Steps:</h2>
<h3>Install Oracle Virtual Box</h3>
1. Head over to Oracle Virtual Box's website and download the application
 <a href=https://www.virtualbox.org/>here.</a>
<h3>Download Windows 10 and Windows Server 2022 ISO</h3>
An ISO file is similar to having the physical disc that helps install the OS. This will help us get to the installation process for both Windows 10 and Windows Server 2022 without the need for a disc reader. 
<br>
<br>
1. Download the multi-edition Windows 10 graphical ISO from Microsoft's website.
<br>
2. Download the Windows Server 2022 from the Microsoft Evaulation Center. (looking for the ISO, not the virtual machine in Azure)
<h3>Spin Up Two VMs:</h3>
<h4>Windows 10 Pro</h4>
1. Open Virtual Box and click "New" to create a new virtual machine.
2. Give the VM a name, a file path to save the data, and select the Windows 10 ISO as the "intended installation".
3. Provision the appropriate resources like RAM and CPU cores for the VM. I chose 4096 MB of RAM and 3 CPU cores.
4. Click "Next" on all the prompts until reaching the install page.

<h4>Windows Server 2022</h4>
5. While Windows 10 Pro is installing, repeat steps 1-4 for Windows Server 2022 

<h3>Configure AD Domain Services</h3>
<h4>Set Static IP</h4>

<h4>Create Groups & Users</h4>
<h4>Create Group Policies</h4>
<h3>Configure Workstation for AD</h3>
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
