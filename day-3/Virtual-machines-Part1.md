Virtual Machines(VM): You are basicaly creating virtual environments that function as virtual computer systems and these virtual computer systems has their own cpu has their own memory and they also have their own hardware,that's why they are called logical computer systems.

Virtualization: You have a physical server that you bought from ibm/hp let's call it as server-1,with the concept of virtualization you will install a hypervisor -> hypervisor is a software that can install virtual machines on your bare metal or physical servers , you are doing logical isolation like vm1,vm2,vm3,vm4,vm5


->why we are calling them as virtual machines?
because they are only logical they don't exist physically so they are vm's.

-> Here you added efficiency using devops

-> what did you add?
Added efficieny

-> how did you added efficicency?
by automating the process using a hypervisor

what are the popular hypervisors?

1. Vmware
2. Xen

using these hypervisors you do a logical separation
like you break the physical server into logical machines or virtual machines and now using the one-team, 1-server, now with the help of hypervisors team 1 can use vm1 , team2 can use vm2, team3 can use vm3, respectively team 4 and 5

-> These virtual machines have their own cpu, memory and hardware 
-> This vm1 is not depending on vm2 for cpu or either memory and it is not depending on vm2 or vm3 or vm4 for hardware so that's why they are called logical computer systems.
-> They have their own memory , they have their own cpu , they have their own hardware but the only difference is instead of physical they are logical servers how is doing this entire process?
-> your hypervisor is doing the entire process your hypervisor is a key that is dealing with your virtual machines.
-> The hypervisor is something that is creating your virtual machines.

Example: What cloud platforms do? 

->Amazon/any cloud provider they build their data centers
-> let's take an area called Mumbai in India what amazon does is if amazon has a data centre in mumbai what that means is they take a huge land and what they do here they install their own physical servers here,they install millions of physical servers.

-> now whatever the user either me or anybody who maks a request to amazon and who selects the region as mumbai, if you go to amazon what you can do is you can ask for virtual machine from aws, in aws you can select your region as mumbai , here what you require is I want one virtual machine in amazon we call it as ec2 instance. in general it is a virtual machine.

->Your request for virtual machine in Mumbai region in AWS. what happens is your request will be sent to one of the data centers and one of these physical servers a hypervisor is installed, in general on all physical servers hypervisors are installed and this hypervisor will create a VM for you and it will share the required details. This how the virtual machines operate.
-> So the world of Virtual Machines operate on hypervisors wheather it is Amazon wheather it is Google wheather it is microsoft, they all have their hypervisors installed on their physical servers and whenever somebody is requesting for virtual machines, hypervisor will give you a virtual machine from one of the physical server depending upon the region that you have selected.
-> Aws has their data centers in singapore in mumbai in us lot more in different regions
-> Whenever the aws feels that's their customer needs a new data center to avoid latency 
-> what is latency: suppose i am in India and I'm creating a virtual machine in mumbai so in comparision because I am located in india in mumbai I will have less latency

-> so this is a data centre in mumbai and what amazon has done is they have installed racks inside (in general servers are installed using racks) I mean there are rack servers and different types of servers so what AWS administrators have done in mumbai they have created multiple racks and they have multiple physical servers.

->Example:
so for example there is physical srver 1, 2.. 100 so these are the physical servers that amazon has installed in mumbai. so each of the physical server can be 100Gb RAM and 100 core processors being a devops engineer what i have done is i am sitting in hyderabad from my personal laptop using some scripts / AWS Portal  i have requested for a virtual machine in mumbai region and the specification that i have requested is 10GB RAM and 12 core processor, let's say i have used some automation / I have manually went to the AWS portal and I have requested for this configuration so now AWS will receive my request, now what AWS will do it will look for the physical server that is ideal for my requirements let's say p1 is alrady occupied now p100 is unused, and AWS feels that my requirement specification let's say p100 has 10000 GB of unused RAM , now aws will ask the hypervisor that is installed on p100 so there is always a hypervisor, so the Aws send a request to the hypervisor to create a virtual machine and Aws send back this virtual machine to user like AWS sent me back with a Virtual machine.what does AWS send? Aws sent Ip address and all the required information to access this virtual machine and end of the day i have logical access to that virtual machine or virtual access to the virtual machine. physically I don't own that virtual machine even though i am paying money to AWS.This is the difference between Physical servers and virtual machines