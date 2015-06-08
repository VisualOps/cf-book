###Example
Here are the examples of rule

- db instance shouldn't have publicIp
	- instance( tagSet["role"] = "db", publicIpAddress!=null )

- web instance should be in public subnet
	- instance( tagSet["Name"] like "^web.*" ).subnet( tagSet["type"] != "public" )