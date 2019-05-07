![](./media/image1.png)

# OCI Overview Hands On Lab
Contents


[Section 6. Create SSH Key Pair (Linux, Mac, Windows client)](#create-ssh-key-pair-linux-mac-windows-client)

[Section 7. Create a Compute Instance](#create-a-compute-instance)

[Section 8. Access the instance](#access-the-instance-and-install-docker)

## 

#

# Create SSH Key Pair (Linux, Mac, Windows client)

SSH keys are required to access a running OCI instance securely. You can use an existing SSH-2 RSA key pair or create a new one. Below are instructions for generating your individual key pair for Linux/Mac and Windows. You can also find instructions on the OCI documentation page.
<https://docs.cloud.oracle.com/iaas/Content/GSG/Tasks/creatingkeys.htm>

## Linux or Mac based Laptop  

1.  **Open** a terminal and type the ssh-keygen command.

    `[opc-instance]$ ssh-keygen -t rsa -N "passphrase" -b 2048 -C "<enteryourkeyname>" -f <enteryourkeyname>-key`

**Note:** *Don't lose your key or forget your passphrase, the key won't be usable without them.  Also, the passphrase isn't required for this lab but should be used for production as a security best practice.*

**ssh-keygen command switch guide:**

    -t – algorithm
    -N – “passphrase” Not required but best practice for better security
    -b – Number of bits – 2048 is standard
    -C – Key name identifier
    -f - \<path/root\_name\> - location and root name for files

![](./media/image32.png)

##### Figure 25: ssh-keygen command

7.  The key pair you generated is now in the current directory.  ls -l command to verify.

![](./media/image33.png)

##### Figure 26: Sample key pair with the example name of team-100.  Your key name should be different.

8.  For Linux and Mac Clients copy the contents of the public key file (.pub). Use an editor or cat command to view the file and copy the key contents. You can use this for the ‘paste key’ dialog when launching an instance.

![](./media/image34.png)

##### Figure 27: Copy ssh key

##  Windows

A third party SSH client needs to be installed for Windows versions prior to Windows 10 in order to generate SSH keys. You can use Git Bash, Putty, or a tool of your choice. This tutorial will use Putty as an example. Git Bash instructions are the same as the Linux instructions above.

**Note:** *If you don’t already have it, download the Putty application and install it on your Windows machine. [<span class="underline">Download Putty</span>](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html).  Puttygen is a utility that comes with the Putty package and is used to generate SSH keys.*

<!-- end list -->

9.  From the Windows start menu, run the PuTTYgen utility

![](./media/image35.png)

##### Figure 28:  PuTTYgen utility command

10. Click the Generate button and follow the instructions for generating random information.

![](./media/image36.png)

##### Figure 29: Generate the key with PuttyGen

11. After the key information has been generated, enter a **passphrase**
    and press the **Save private key** button to save the key to your
    system.

**Note:** *A passphrase is not required but recommended for stronger security.*

![](./media/image37.png)

##### Figure 30: Putty save key dialog

12. The private key should have the .ppk extension. Store it in a folder that’s easily accessible.

![](./media/image38.png)

##### Figure 31: Saving the private key

**NOTE:**  *We will not use the ‘Save public key’ option in PuttyGen, as the keyfile is not compatible with Linux openSSH. Instead, we will copy and paste the key information into a text file.*

13. Left click on the Public key information and choose ‘Select All’ to select everything in the key field. Then left click again and copy the selected information to the clipboard.

![](./media/image39.png)

##### Figure 32: Save all and copy key to clipboard

14. We will use the clipboard to paste the key information in the next step but you can also save your public key to a text file with Notepad. Open a plain text editor and paste the key information. Name and save the file with a .pub extension.

![](./media/image40.png)

##### Figure 33: Key pasted and saved with Windows Notepad

15. Close the Puttygen application

# Create a Compute Instance

1.  Navigate to the OCI console, use the top left hamburger menu and
    choose **Compute \> Instances** to open the Instance Creation menu.

![](./media/image41.png)

##### Figure 34: Create Instance Menu item

16. Click the **Create Instance** button

![](./media/image42.png)

##### Figure 35: Create instance button

![](./media/image43.png)

##### Figure 36: Information required to create an instance

17. Enter information to create your compute instance.

**Note:** *Each team has been assigned an Availability Domain in order to help conserve resources in the demo lab environment. Please use your assigned Availability Domain.*

| **Name:**                | **\<instance name\>\_*your\_compartment\_name*** |
| ------------------------ | ------------------------------------------------ |
| Availability Domain: | AD assigned to your team AD1, AD2, or AD3   |
| Operating System:    | Oracle Linux 7.6                            |
| Instance Type:       | Virtual Machine                             |
| Shape:               | VM.Standard2.1                              |
| Boot Volume:         | Default                                     |
| SSH Key:             | Choose SSH Key file or Paste SSH keys      |
| Compartment:         | Your team compartment* (*ex:* team-100)     |
| VCN:                 | Your VCN* (*ex:* Team 100 VCN)              |
| Subnet Compartment:  | Your subnet compartment* (ex: team-100)     |
| Subnet:              | Public Subnet in your compartment*            |

18. In the **Add SSH Key** section you can select the SSH key file from your system or paste directly from the clipboard (if you’ve saved that information from the key generation step earlier)

![](./media/image44.png)

##### Figure 37: Choose SSH Key option

![](./media/image45.png)

##### Figure 38:  Paste SSH key option

19. In the Configure networking Section leave the default VCN and subnet information and click **Create**. 
![](./media/image46.png)

##### Figure 39: Create compute instance dialog

Your instance will begin provisioning and should be in the available state within a few moments.

![](./media/image47.png)

##### Figure 40: Instance provisioning

After a few moments, the icon will turn green and the title will change to RUNNING.

![](./media/image48.png)

##### Figure 41: Running instance and Primary VNIC information

20. Take note of the assigned Public IP Address you will need this to access the instance later.  

# Access the instance  (Change this section to just access - no Docker)

We will use an SSH terminal session to access the compute image. From there we will install Docker and GIT.

## SSH Key access for Linux/Mac 

1.  Use your favorite terminal program and issue the below ssh command to connect. Use the public IP address of your instance as referenced in the above screenshot.  (*The IP address listed is for example only, please use your own)*

21. Navigate to the subdirectory where you key is stored and issue the following command.

    `ssh –i <your private key name> opc@<your ip address>`

![](./media/image49.png)

##### Figure 42: SSH connection to running instance

## SSH Key access for Windows with Putty

1.  For Windows clients, open Putty. With the Session category selected, enter the IP address for the instance you want to access and select SSH from the radio buttons (port 22).

![](./media/image50.png)

##### Figure 43: Putty session information

22. In the Connection category, choose **Data** and enter ‘opc’ as the Auto-login username.

![](./media/image51.png)

##### Figure 44: Putty auto-login information

23. In the **Connection \> SSH \> Auth** category, use the Browse button to navigate and load the .ppk file you created earlier with Putty.

![](./media/image52.png)

##### Figure 45: Putty private SSH key

24. Navigate back to the **Session** category, enter a name in the **Saved Sessions** field and choose Save. This will save your SSH terminal session for use later without having to re-enter the information.

v![](./media/image53.png)

##### Figure 46: Putty Save SSH Session

25. Click on **Open** to connect to the instance.

26. Choose **Yes** on the alert message:

![](./media/image54.png)

##### Figure 47: Putty security alert

27. You will be logged into the compute image:

![](./media/image55.png)

##### Figure 48: Successful Putty instance login

![](./media/image99.png)

##
