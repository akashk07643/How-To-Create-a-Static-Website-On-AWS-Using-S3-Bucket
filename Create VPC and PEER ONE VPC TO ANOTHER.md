Link-> https://www.youtube.com/watch?v=KmNZo741hsg\&list=PLlfy9GnSVerQK70g5dFWZ0hFKv6PeEPW0



##### Q-> CREATE A VPC AND GET IT PUBLIC SUBNET ACCESS :-



1. Create VPC->VPC only ->name ->IPv4 CIDR("10.0.0.0/24"=256-5=251 ip address) ->Tenancy(Default) ->Tags(->Value "VPC name") ->Click "Create VPC" .
2. Go to subnets ->Create Subnets ->VPC ID (Select Vpc Name Which You Have Created) ->Subnet name ->Availabilty Zone-> Ipv4 subnet CIDR(10.0.0.0/24) ->Click Create Subnet .
3. Go to Internet Gateway ->Click on Create int.. Gate.. ->Name ->Create .
4. Go to Route Table ->Create route table ->Name ->VPC("VPC NAME" ->Create .
5. GO to Route table that u have created (Open it) ->Subnet association ->edit Subnet association -> Select your subnet ->save association.
6. Inside Subnet association ->click on Subnet id that u created -> select your subnet ->Action ->edit subnet setting ->Enable auto-assign public IPv4 address ->save .
7. Go to internet Gaterway -> attach to VPC ->Select available Vpc -> Attach to internet .
8. Route table ->select route that u created ->Routes ->Edit Routes ->Add route ->write (0.0.0.0/0)->select option(internet gateway) and Select your internet gateway ->Save .



##### To Check Your VPC Is Running or Not :-

1. Go to Services ->EC2 -> Launch Intance ->Name ->ubuntu ->key pair -> Network setting(Edit) ->select VPC that we created -> Subnet that we have created ->Auto assign Public IP(Enable) ->Add security Group rule ->Type(HTTP) ->Source (10.0.0.0/24) ->Launch Instance .



###### CONNECT ONE VPC TO OTHER USING PEERING VPC SERVICE:-

1. Create a New Vpc ->vpc name ->IPv4 CIDR(192.0.0.0/16) ->Tenancy(Default) ->Create VPC .
2. Create Subnet ->name of new PUBLIC subnet -> subnet setting ->Name ->Availabity zone ->IPv4 subnet CIDR block ->192.0.0.0/24 .
3. SAME PROCESS  but instead of PUBLIC->WRITE PRIVATE and in CIDR Block ->192.0.128.0/17 ->Create subnet .
4. Internet Gateway ->Create IG ->Name ->create IG.
5. Go to  action ->attach to VPC ->Available VPC(NEW VPC)->Attach IG .
6. CREATE ROUTE TABLE -> NEW NAME ->VPC -> SELECT NEW VPC NAME ->Create .
7. Inside subnet association ->edit ->select new public subnet ->save association .
8. beside subnet association "click on routes ->edit ->add routes ->0.0.0.0/0 ->select internet gateway-> and select new gateway that u have created ->save   (TIME=1:20:00)
9. **follow the step ->To check your vpc running or not ->just change instance name and try to connect.**

   \*\*\*\*\***NOW LETS PEER BOTH VPC FROM ONE ANOTHER\*\*\*\*\***
   
   ---
10. peering connection ->create->peering name ->select local vpc to peer with select(old vpc) VPC ID(Accepter)->select new vpc->Create Peering  connection .
11. Go to peering connection ->select the peering u created ->action -> accept request .
12. Go to instances ->select old vpc ->security group -> select link prent down -> edit inbound rules ->add 2 rule ->1. all ICMP-IPv4 10.0.0.0/24 >description (old ip name) ->done. 2. all ICMP-IPV4 192.0.0.0/16 ->description (new ip name) .
    
13. Go to instances ->select new vpc ->security group -> select link prent down -> edit inbound rules ->add 2 rule -> 1. all ICMP-IPV4 192.0.0.0/16 ->description (new ip name) ,2. all ICMP-IPv4 10.0.0.0/24 >description (old ip name) ->done .
14. go to route table ->select **old route table** ->click on route table id->edit routes->add route->**new vpc ip address** ->peering connection ->select (old peering connection) ->save .
15. go to route table ->select **new route table** ->click on route table id->edit routes->add route->**old vpc ip address** ->peering connection ->select (new peering connection) ->save .
16. **And now go to old ec2 instance and type ping 192.0.0.34(you will see data is recieving) .**















































































