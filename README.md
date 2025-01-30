# Linux
Account Setup
In the first step, I have created a Microsoft Azsure account using our university email address. Then, my microsoft azsure account is successfully created and I have recevied $100 worth of credit which helps me to purchase different types of useful learning environment.

# Create Virtual Machine
I have created a virtual machine where I can learn and do some projects for this course.
Then, I named the machine "lab-robotics" and then I have select the no infrastructure redundancy required option and Trusted launch virtual machines security type.
I choosed Ubuntu Server 24.04 LTS - x64 Gen2 server and B series version 2 which is Standard_B21s_v2.
After completing all the steps, I got a key and I have selected the connect option and choose the native ssh option.
There is a copy and execute SSH command button, I have pasted the key which I have got earlier.
Then open the windows powershell and paste the link generated link there and I reached in the Linux virtual machine.
It help us to use Linux in windows laptop without installing it.

# Linking my GitHub account to my HAMK email
I created a new repository named "Linux" for the assignment.
Then I linked my HAMK email as a secondary mail for version control.

# screenshoot
![alt text](linux.jpg) 
![alt text](<microsoft azure.jpg>)


# assignment 3
# User Management and File System access
I have created user accounts on my Linux system to manage access 
and permissions.

First, I created a user named tupu by running the sudo adduser tupu command.
This automatically created the home directory /home/tupu, set /bin/bash as 
the default shell, and prompted for a password setup.

Then, I created another user lupu using sudo 
useradd -m -d /home/lupu -s /bin/bash -G lupu lupu. 
This command manually set the home directory,
assigned /bin/bash as the default shell, and
added lupu to the lupu group. After that, 
I set a password for lupu using sudo passwd lupu.

Next, I added a system user hupu with restricted access 
using sudo useradd --system --shell /bin/false hupu. 
This prevents hupu from logging in interactively.

To grant administrative privileges, I opened the 
sudoers file using sudo visudo and added the following
lines at the end:

        tupu ALL=(ALL:ALL) ALL  
        lupu ALL=(ALL:ALL) ALL

Alternatively, I could add both users to the sudo group using:

        sudo usermod -aG sudo tupu  
        sudo usermod -aG sudo lupu  

To verify their group memberships, I used groups tupu and groups lupu.

Then, I set up a shared directory for tupu and lupu. First, I created a
directory using sudo mkdir /opt/projekti. Then, I created a group named 
projekti using sudo groupadd projekti and added both users to it with:

        sudo usermod -aG projekti tupu  
        sudo usermod -aG projekti lupu  

After that, I changed the group ownership of the directory using sudo chown
:projekti /opt/projekti and modified the permissions with sudo chmod 770 /opt/projekti, 
ensuring that only tupu and lupu could access and modify files.

To make sure all new files inside /opt/projekti inherit the projekti group, 
I applied sudo chmod g+s /opt/projekti.

Finally, I verified my setup by running groups tupu, groups lupu, and checking
the directory permissions using ls -ld /opt/projekti. The expected output was:

        drwxrws--- 2 root projekti 4096 Jan 30 18:37 /opt/projekti  


# screenshoot
![alt text](assignment_3_ss.jpg)