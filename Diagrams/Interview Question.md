# Domain: Cloud Security

## Question 1: Cloud Access Control
### How would you control access to a cloud network?

How to control access to a cloud network? Controlling access to a cloud network is varied and depends on the resources that are feasible for the company. 

For instance, in my bootcamp project, I was allocated with a Microsoft Azure Cloud Network Resource Group, which I configured relying on Network Security Groups around the Virtual Network.
For the purpose of the project, the Network Security Groups sufficed enough to protect the Virtual Network(s) resources, therefore only leveraged the use of allow/deny lists in the environment. 
Those rules allowed me to block external inbound traffic to my Web Server VMs while only allowing traffic from my Jump-box VM.

In order to harden the Virtual Network, I restricted external traffic on port 22 to only allow my Jump-box vm to accept traffic from my dedicated IP Address at home; 
while at the same time I only allowed SSH traffic from the Jump-box VM to the internal resources or Web Servers. And, a similar configuration was set up for port 80 to serve web traffic.

The Jump-box served as the orchestration terminal, which in a sense served as a soft router/firewall, all incoming traffic to the Web Servers was routed through the Jump-box.
Obviously, in this particular scenario, there are advantages and disadvantages for such an implementation. One could make the case that for a small business with a limited budget, 
this setup would be ideal.

There are other solutions that can be implemented in place of a Jump-box, for example adding a physical firewall, or a more robust software firewall to configure internet traffic, and also a VPN implementation would be ideal. 
I didn’t configure a VPN given that I configured a small number of VMs, and it would’ve added complexities to the configurations.

I am all in for VPN implementations, and I recommend their use for anyone because of the extra layer of security that allows only authenticated users to access the company’s network resources.
And, although VPNs provide more security, we are only as secure as our weakest link; user credentials compromises are always one of our weakest points.
