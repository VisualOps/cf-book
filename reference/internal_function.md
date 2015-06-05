# Function

Some resource have function which can help user easy to write rule:

- instance
	- has_sg_rule - sg related to instance(including not parmary network interface) has this sg rule
	- has_not_sg_rule - sg related to instance do not has this sg rule
	- has_invalid_ami - ami using by the instance is invalid
- lc
	- has_invalid_ami - ami using by the instance is invalid
- all resource
	- connected - resource on left has connected to resource on the right, like vpc.connected(resource=["igw"])
	- unconnected - resource on the left do not connected to resource on the right


#### Example
- instance.has_sg_rule(ipPermissions.fromPort=80)
- instance.has_not_sg_rule(ipPermissions.fromPort=22)
- vpc.connected(resource=["igw", "cgw"])
- subnet.unconnected(resource=["instance"])
- instance.has_invalid_ami()
- lc.has_invalid_ami()