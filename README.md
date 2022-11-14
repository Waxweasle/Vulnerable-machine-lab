# Vulnerable-machine-lab
Create a vulnerable machine and locate attackers around the world.

### Technologies used:
- Azure
- Azure sentinel
- Powershell (script)
- ipgeolocation.io

## Virtual machine set-up
1) Once signed up/ logged in to Azure, create a Windows 10 Pro virtual machine and assign it to a resource group for this lab. (MAKE A NOTE OF USERNAME AND PASSWORD)
![VM setup](image.jpg)
2) Proceed through set up and once at Networking, in "NIC network security group" click Advanced - Create New.
3) Remove any exisiting security groups and add an inobund rule as shown below. This increases the visability and vulnrability of the machine.
![VM setup](image.jpg)
4) Finalize VM steps and wait for it to be created.

## Log Analytics set-up - this allows logs to be drawn from the VM.
1) Head to Log analytics within Azure - and create a new workspace.
2) Simply create the workspace and make sure it is linked to the same resource group you just created for the VM.
3) Within the left menu click Virtual Machines - Your VM - Connect to link your Log workspace to your VM.
4) Allow log gathering by heading to Microsoft Defender for the Cloud, - Pricing & settings - Your Log workspace - Turn on Azure defender.
5) Also enable data collection by Data collection - Allevents (check this box).

## Azure Sentinel set-up.
1) Within Azure, head to Microsoft Sentinel - Create - Click your Log workspace

## Geolocation API set-up.
1) Head to https://ipgeolocation.io/, make an account and paste you API key into the Powershell script attached to this repo.

---

## Putting it all together
1) Get your VM IP from the VM tab as shown below.
2) Use RDP on your own machine to log into the VM, using the IP provided and your name and password from the VM set up stage.
3) Head to Windows Firewall within the VM and turn OFF all firewall features, making it discoverable to others.
4) This lab focuses on using a failed log-in attempt to locate an attacker. This event has the Event ID of 4625 within Event Viewer.



