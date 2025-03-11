# Terraform Provider Infoblox.
 Website: https://infoblox.com
 
The Terraform provider for Infoblox POC/Lab is a Terraform plugin to enable full lifecycle management of CSPs resources. The provider is maintained internally by Infoblox TME team.




##   Infoblox Lab Example
The goal is to illustrate the various capabilities of Infoblox functionalities.

The Demo infrastructure used is a basic deployment that creates and manages resources in either AWS, Azure of GCP. The examples utilize standard modules from the Terraform registry to set up networking, create virtual machines, and other resources. Each example also includes a custom modular design that utilizes variables and modules to make the code reusable and scalable.

The module structure is also aplicable for INfoblox  resources as well which will be treated as module. The table below is per Region setup.

|     AWS              |      Azure          |
| -------------------- | ------------------- |
|  6x VPC              | 2x Vnet             |
|  2x Internet Gateway | 2x RG               |
|  6x Subnet           | 2x Subnet           |
|  6x Virtual Machine  | 2x Virtual Machine  |
|  1x TGW ( optional ) | 1x vWAN( optional ) |
|  6x SSH Key-Pair     |                     |

Every module has a possibility to spin up TGW as an option. SSH Key-pair is also created with an option to download public key to the local system.

The script lets you generate SSH private key on the fly using tls_private_key resource. I see people using tls_private_key who don’t want to keep the manual activity of creating the key outside terraform - This is suitable for LAB demo. But this comes at a cost. 

## NOTE: The private key generated by tls_private_key is stored unencrypted in your terraform state file which is unsafe.Never use this in the production.


### **Diagram is coming...** 🛠️  
_(The architecture diagram will be added soon!)_


## Modular Framework

This Demo example demonstrates a modular structure approach in Terraform, which allows the infrastructure to be easily scaled and managed. By using modules, resource configurations are organized and encapsulated, making it easier to create and manage infrastructure resources that share common functionality and can be replicated as needed.

The use of modules also allows for easier maintenance and updating of the resources over time, and it enables the reuse of resource configurations across different projects.

With this modular approach, the infrastructure resources can be deployed and managed easily, making the code more scalable and maintainable over time.


## Outputs

aws_ec2_public_ip_eu

Public IPs of EC2 instances in EU Region

aws_ec2_public_ip_us

Public IPs of EC2 instances in US Region


