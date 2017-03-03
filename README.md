# sysprep-image

Steps for sysprep on Windows 10 1607
Download the latest ADK version. Below is the link :
https://developer.microsoft.com/en-us/windows/hardware/windows-assessment-deployment-kit

Run the Windows 10 Installation

Disable first sign-on animation(optional)
Open Group Policy Editor

Local Computer Policy->Computer Configuration->Administrative Templates->System->Logon->Show First sign-in animation->Disable

Login with an account within the Administrator Group or with Domain Administrator privileges. 

Remove local Administrator password. 

Go to c:\windows\System32\sysprep\sysprep.exe
Select in the dropdown box 'audit', Click on 'Generalize' and then 'Reboot'.

After system reboots, it will login as Administrator and you will not be prompted for a password if you removed the password correctly. 

After booting is complete,remove all the user profiles except Administrator and Default. They can be found in control panel/user profiles

Then go to 'This PC', click 'Manage' and find 'Local Users and Groups. Delete all groups and users except for Administrator and guest.
Other settings: Enable Administrator if necessary. Add network printers

To activate the inactive administrator account, run the command net user administrator /active:yes
If you want to enable the guest account as well run the command net user guest /active:yes

Run Disk Cleanup or CC cleaner

Download Updates

Second part of sysprep - Capture the image 

Go to c:\windows\System32\sysprep\sysprep.exe
OOBE,Generalize, Shutdown

Power down PC
Turn on PC and halt boot process. Do not boot to local drive. Boot to a WinPE boot disk

at prompt type diskpart




