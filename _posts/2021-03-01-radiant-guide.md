# How to create a VM on Radiant

Go to radiant.ncsa.illinois.edu and log in

Should bring you to a webpage like this:

![](/images/Figures/Radiant_overview.png)

Click on instances and then click Launch Instance.
![](/images/Figures/Radiant_instances_red.png)

From here you will start building the VM

## Name the VM
Here you will give a name and a description for your VM. You do not have to touch the other two options.
![](/images/Figures/Radiant_Name.png)
## Pick a Source

Here you will pick what operating system to run on your VM, along with how large you want the volume size to be and a few other options.
In this example, I chose an ubuntu VM with 50 GB storage.

![](/images/Figures/Radiant_Source.png)

If you already have a volume that you want to use instead of a new one, click No on Create New Volume and then add the volume to the machine.
## Pick a Flavor

This is where you pick the size you want your VM to be. In this example, I choose a medium sized VM.
![](/images/Figures/Radiant_Flavor.png)
## Networks

When you open this tab, you will see two network options: bbdd and ext. Add them both. 
Bbdd is for the internal communication within Radiant and ext is for external communication, 
and both are needed if you would like to use your VM.
![](/images/Figures/Radiant_networks.png)
## Security Groups

If you would like to use your VM through SSH, make sure to allow remote SSH in this tab by moving it allocated.
![](/images/Figures/Radiant_SecurityGroups.png)
## Key Pair

In here, you can either create a new key pair to be used for loging in to this vm, or you can create a new one. To create a new key click create a new key, give it a name, and select ssh key as the key type. Then move the newly created key up to the allocated section.

If you want to then use this key to ssh, make sure you have a way to access it from wherever you are going to try to ssh from. For example, if you are going to ssh locally from your computer to the VM, you might want to save the key locally to your computer. To save the key locally, expand the key and then copy and paste the public key into a file and save it.
## Configuration

Finally, make sure to check the Configuration Drive button on this tab
![](/images/Figures/Radiant_configuration.png)


This is all that is requried to make your VM! When you are done, click Launch Instance and this will build your VM.

To SSH into your instance, use the IP of your instance given under ext-net in the instance tab. The username will depend on what operating system you picked.
For example, if you made an ubuntu system with IP 141.142.240.42 and saved the key in a file named key.pem, then you would enter the following command into your command prompt


ssh -i key.pem ubuntu@141.142.240.42

