# AWS VPC Network

> The core differentiation between a public and private subnet in VPC
is defined by what that subnet's default route is, in the VPC routing tables 
* [Reference](http://stackoverflow.com/questions/22188444/why-do-we-need-private-subnet-in-vpc)

* Public
* Private
* NAT

## NAT (Network Address Translation)

* For instances with only a private IP address, there's an alternate way of outbound access to the Internet. This is where Network Address Translation and a NAT instance come in.
* It's not the IG but receive traffic by VPC from private machines by replacing source IP address on the packet with its own public IP address
* [AWS Documentation](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_NAT_Instance.html)
* [Joinc Docs](http://www.joinc.co.kr/modules/moniwiki/wiki.php/Site/cloud/AWS/VPCManagement)
* [Blog: NAT CloudFormation](http://mrbluecoat.blogspot.kr/2014/11/aws-cloudformation-template-for-vpc.html)
* NAT SecurityGroup
    * Allow inboud traffic only from private (10.0.1.0/16)
    * Allow all outbound traffic
    * Attack public subnet