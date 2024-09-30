### Creating VPC Peering

Mumbai region
Create VPC > vpc only > name-test-vpc >range – 10.0.0.0/16 > create vpc
Internet getways  > test-igw  > attach to vpc  > attach
Subnet > create subnet > my vpc > name-test-vpc > 
>public-subnet>zone>10.0.0.0/16 > 10.0.0.0/24
>private-subnet>zone>10.0.0.0/16> 10.0.1.0/24

EC2 > instance > name-web-server > network-test vpc > subnet-public > ip-enable > create security group > test-vpc-sg > inbound rules > HTTP
Route table > create new > public-rt >vpc >create
Edit rout > 0.0.0.0/0 > add internet gateway > igw…

In terminal > connect web server > 
Sudo su –
1  yum install httpd -y
    2  cd /var/www/html/
    3  echo "This is my web app server" >index.html
    4  cd
    6  systemctl start httpd
    7  systemctl enable httpd
Check by ip if the server is working

Launch new instance > db-server > net setting > edit > private > existing sec group > common security group > launch
Security > edit > add rule > ICMP-IPv4  > save
#ip a s
Ping …..id
ll 
vim …..pem < insert the key which is on the notepad 
chmod 400 ….pem

copy ssh of new instance > open in same terminal >
sudo su –
Create nat gateway > test-ngw > public > public > create
Route table > create table > private-subnet > edit rout > add NAT gataway
#ping google.com.
Do the same process in Singapore region take the id as 20.0.0.0/16
In bothe terminal
#ssh-keygen
cd.ssh
cat id_rsa.pub   (Exchang the keys)
vim authorized_keys 
come out of ssh
in Mumbai region create vpc peering > my acc > same acc > another region > Vpc id from Singapore > create peering
in Singapore > select and accept req > routing table > pub rt> edit > add rout > 10.0.0.0/16> pearing connection > id save changes
in mum > rout > 20.0.0.0/16
after this ping with ip a s of each others ip
Mumbai - # cat > ghostrider.txt
This is ghost rider
Ll
Scp ghostrider.txt root@20.0.0.118:/tmp
Singa- cat > Dracula.txt
I love vampires
Ll
Scp Dracula.txt root@10.0.0.118
         ………………………………………:/mnt
Cd/tmp/
Ll
