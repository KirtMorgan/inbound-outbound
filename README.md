# INBOUND & OUTBOUND for a Private Subnet

- The private subnet should not be accessible to the user.
- The private subnet is being used to store the database.

## INBOUND Rules

### Allowing the Mongo database to receive updates
Custom TCP Rule,
TCP (6),
1024 - 65535,
10.22.1.0/24,
ALLOW

### Allowing the Mongo database to receive requests for data
Custom TCP Rule,
TCP (6),
27017,
10.22.1.0/24,
ALLOW

## OUTBOUND Rules

### Allowing the Mongo database to request updates
Custom TCP Rule,
TCP (6),
1025 - 65535,
0.0.0.0/0,
ALLOW

### Allowing the Mongo database to send data
Custom TCP Rule,
TCP (6),
27017,
10.22.1.0/24,
ALLOW

# Research

## What is ACL?

A network ACL is an optional layer of security that acts as a firewall for controlling traffic in and out of a subnet.

## What are Security Groups?

A security group acts as a virtual firewall for your instance to control inbound and outbound traffic.

## How do they differ?

The difference between ACL and a Security Group is that ACL is used within a network environment and Security Groups are used within a virtual environment, however the thing they share in common is that they are both security firewalls that control traffic.

## What is Bastian Host?

A bastion host is a special-purpose computer on a network specifically designed and configured to withstand attacks. The computer generally hosts a single application, for example a proxy server, and all other services are removed or limited to reduce the threat to the computer. It is hardened in this manner primarily due to its location and purpose, which is either on the outside of a firewall or in a demilitarised zone (DMZ) and usually involves access from untrusted networks or computers.
