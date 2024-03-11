CloudFormation Template Overview:

     +---------------------------------------------------+
     |                 AWS CloudFormation                |
     |                                                   |
     |             +-----------------------+             |
     |             |         VPC           |             |
     |             +-----------------------+             |
     |              |        |          |                 |
     |              |  Public Subnet   |                 |
     |              |------------------|                 |
     |              |    Private Subnet |                 |
     |              +-------------------+                 |
     |                                                   |
     |        +----------------+     +----------------+  |
     |        |  Public Route  |     | Private Route  |  |
     |        |     Table      |     |     Table      |  |
     |        +----------------+     +----------------+  |
     |                                                   |
     |        +-----------------------+                  |
     |        |  Internet Gateway     |                  |
     |        +-----------------------+                  |
     |                                                   |
     |        +-----------------------+                  |
     |        |  Public Instance      |                  |
     |        |    (Web Server)       |                  |
     |        +-----------------------+                  |
     |                                                   |
     +---------------------------------------------------+

Description:
- This CloudFormation template creates a Virtual Private Cloud (VPC) with one public subnet and one private subnet.
- Each subnet has its associated route table.
- An Internet Gateway is attached to the VPC to allow connectivity to the internet from the public subnet.
- An EC2 instance (web server) is created in the public subnet with a web server configuration using User Data Script (UDS).
- The web server instance in the public subnet will have a public IP address.
- The CloudFormation stack outputs the public IP address of the web server instance.

Note: The private subnet instances do not have public IP addresses for security reasons.

