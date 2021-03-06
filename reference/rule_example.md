###Example

Here are some rules examples:

- db instance shouldn't have publicIp  
	- instance( tagSet["role"] = "db", ipAddress!=null )

- web instance should be in public subnet  
	- instance( tagSet["Name"] like "^web.*" ).subnet( tagSet["type"] != "public" )

- AMI of lc should be existing  
	- lc.has_invalid_ami()

- elb name starts with ‘test-’ and should be in us-east-1a and us-east-1b  
	- elb(  
        LoadBalancerName like "^test-.*",  
        AvailabilityZones has not ["us-east-1a","us-east-1b"]  
    )

- elb listener should contains HTTP 80  
	- elb( ListenerDescriptions.Listener != { "LoadBalancerPort" : 80, "Protocol" : "HTTP" })

- web instance, should close TCP 22 port  
	- instance( tagSet["role"] = "web" ).has_sg_rule(ipPermissions = {"fromPort": 22, "ipProtocol":"tcp"} )

- web instance, should close 22 port  
	- instance( tagSet["role"] = "web" ).has_sg_rule(ipPermissions = {"fromPort": 22} )  
	- instance( tagSet["role"] = "web" ).has_sg_rule(ipPermissions.fromPort = 22 )

- each instance should have owner  
	- instance( tagSet["Owner"] = null )  
	- instance( tagSet["Owner"] = "" )

- "Name" of tagSet isn't present  or tagSet["Name"] is ""  
	- instance( tagSet["Name"] = null )

- "Name" of tagSet is present  
	- instance( tagSet["Name"] != null )