# General Policy Config for PA Firewall

### Table of Contents

### Information Needed to complete:
* PA MGMT (IP or FQDN)
* PA username and password

### NAT Policy
We will create a NAT policy that allows trust to NAT outbound to the Internet.

1. From the PA select Policies and NAT on the left side.\
![nat_location](images/nat_location.png)
2. Click on add in the bottom left.
3. Under General give it a logical name, and description.\
![nat_general](images/nat_policy_general.png)
4. Under Original Packet set the source zone to trust and the destination zone to untrust\
![nat_original_packet](images/nat_original_packet.png)
5. Under translated packet set the Source as Persistent Dynamic IP and Pork
6. Address type to Interface Address
7. Interface to ethernet1/1 (untrust)
8. IP address select the interface IP you assigned to ethernet1/1\
![nat_translated_packet](images/nat_translated.png)
9.  Press ok and it should look similar\
![nat_final](images/nat_full_policy.png)
10. Commit your changes.

### Trust to Untrust Internet Policy
We will create a basic security policy that allows trust zone to access any website.

1. From the PA select Policies and Securiy on the left side.\
![policy_start](images/policy_start.png)
2. Click on add in the bottom left.
3. Under General give it a logical name and description.\
![policy_general](images/policy_general.png)
4. Under source set the source zone to trust.\
![policy_source](images/policy_source.png)
5. Under destination set the source zone to untrust.\
![policy_destination](images/policy_destination.png)
6. Under application make sure any is checked.\
![policy_application](images/policy_application.png)
7. Under Service/URL Category make sure application-default is selected above service and any is checked under URL category.\
![policy_service](images/policy_service.png)
8. Under Action make sure traffic is set to allow.
![policy_action](images/policy_action.png)
9. Press Ok and it should look similar.\
![policy_final](images/policy_final.png)
10.  Commit your changes.

### Testing from SSH
1. SSH into your PA firewall.
2. From the cli type in ```ping source {IP of ethernet1/1} host 8.8.8.8```\
![ping](images/ping_validate.png)
3. If you want to quickly find your ethernet1/1 address from the CLI enter in ```show interface logical```\
![interface](images/interface_logical.png)