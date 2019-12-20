<!-- TITLE: Ip Restrictions -->
<!-- SUBTITLE: A quick summary of Ip Restrictions -->

# Firewall and IP Restrictions

## MVS/RS1
For connecting to RS1 (DPK, MVS, FOXPK, Samples/showcase.thinkjam.com) via SFTP, users IP address needs adding to the firewall.

1. ssh into rs1.thinkjam.com (http://wiki.thinkjam.com/studio/development-team/server-descriptions)
2. `cd scripts`
3. `nano ufw-rules.sh`
4. add user IP address (if Developer or Devops, add 27618 as port too for ssh access)
5. `sudo ufw allow from 82.3.160.91 to any port 22 `
6. `sudo ufw allow from 82.3.160.91 to any port 27618`
6.  save file (ctrl + x)
7.  run script: `./ufw-rules.sh`

## Internal sites
Internal facing sites run in the same way. By ssh-ing in to the server you need as root, ufw scripts should be located in a scripts server.

## AWS
Some sites site in our AWS buckets. if any connection is needed here, login via one login to **amazon web services**

Go to **EC2 ->  Security Groups**
Select the necessary group and update/add the rules as necessary

![Screenshot 2019 09 23 At 15 26 37](/uploads/screenshot-2019-09-23-at-15-26-37.png "Screenshot 2019 09 23 At 15 26 37")




