# VPC Cloudformation

AKA The Black Hole that will suck you into an infinite spiral of darkness and destruction... Started with multiple VPCs
for each environment, internal and external, plus an infrastructure VPC, before realizing that the int/ext structure
should be done with different subnets. Abandoned the overly complex example that was progressing in cb99-networks.json &
cb99-vpc.json, for the simpler cb99-w3-vpc.json which successfully completes the requirements for the assignment.

*   create VPC
*   create IGW
*   attach IGW to VPC
*   create RT
*   create IGW route
*   create private subnet
*   create public subnet
*   create RTA for public subnet
