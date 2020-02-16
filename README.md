# <p align="center"> Jupyter_Python_AWS

**=======================================================================**
## Process walk-through for Python Jupyter Server installation on Amazon AWS

**----------------------------------------------------------------------------------------------------------------------------**

### Creation of VPC instance for Jupyter :
Step 1 : Login in to your AWS account 
Step 2 : Create a VPC (CIDR: 10.0.0.0/16) like DC_Jupyter_VPC
Step 3 : Create a public subnet (CIDR: 10.0.0.0/24)
Step 4 : Create an Internet Gateway and attached to the VPC ( DC_VPC_Intgw11) 
Step 5 : Create and edit the Route table. (DC_SC_Grp_Jupyter)
Now Click on the subnet association tab and associate this route table to the subnet
Create security create a security group [Inbound / Outbound Rules] in which we should open the port 8888 which has been associated with Jupyter notebook - Python Server.
! [VPC-SecurityGroups-InboundRules-Step5] VPC-SecurityGroups-InboundRules-Step5.png
! [VPC-SecurityGroups-OutboundRules-Step5] VPC-SecurityGroups-OutbounRules-Step5.png  

 
VPC for Jupyter Notebook has been created

! [VPC-Jupytre-Instance] VPC-Jupytre-Instance.png
 
**-------------------------------------------------------------------------------------------------------------------------------**

EC2 AWS Jupyter Notebook Server Connection :
Now Create your EC2 for Jupyter server instance
Step 1 : Select “Ubuntu Sever 1804 LTS [HVM], SSD volume Type”
! [AWS-Jupyter-EC2-Ubuntu-Server-18-04] AWS-Jupyter-EC2-Ubuntu-Server-18-04.png

 
Step 2 : 
Now “Choose Instance Type” page no need to update anything only will have to select VPC.
Step 3 :
 Go to the Configure instance details page check for Network & Subnet.
In advanced option, will have to copy the script which downloads the Rserver package and install. Also this script enable User Id and Password.
! [AWS-Jupyter-Configure_Instance_Details] AWS-Jupyter-Configure_Instance_Details.png

Step 4 : Now Next Page “Add Storage” and “Add Tags” no need to update anything.
Step 5: Finally, “Configure Security Group” page will have to click on Review and Launch

! [AWS-Jupyter-EC2-Review&Launch] AWS-Jupyter-EC2-Review&Launch.png

  
Now wait for few seconds to change Instance State to change “running” for DC_Jupyter_Instance.

! [AWS-Jupyter-EC2-Dashboard-RunningStatus] AWS-Jupyter-EC2-Dashboard-RunningStatus.png

 
Install pip
sudo apt-get update -y
sudo apt-get install python3-pip
To launch script from Python
python3 ec2_python_script.py

Launch Jupyter Notebook
Now, Type on the browser page, the public IP address of EC2 instance(34.207.166.183), Jupyter Port (8888).

! [Browser_Launch_Jupyter] Browser_Launch_Jupyter.png
 


Thanx!
