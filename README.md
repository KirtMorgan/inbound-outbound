# INBOUND & OUTBOUND for a Private Subnet

The private subnet should not be accessible to the user.
The private subnet is being used to store the database

## INBOUND Rules

### Allowing the Mongo database to receive updates
Custom TCP Rule
TCP (6)
1024 - 65535
10.22.1.0/24
ALLOW

### Allowing the Mongo database to receive requests for data
Custom TCP Rule
TCP (6)
27017
10.22.1.0/24
ALLOW

## OUTBOUND Rules

### Allowing the Mongo database to request updates
Custom TCP Rule
TCP (6)
1025 - 65535
0.0.0.0/0
ALLOW

### Allowing the Mongo database to send data
Custom TCP Rule
TCP (6)
27017
10.22.1.0/24 
ALLOW
