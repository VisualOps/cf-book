# Function


Some resources have some functions helping you to easily write a rule:

- instance
	- has_sg_rule - Security Groups related to the instance (without including primary network interface) containing the specified rule
	- has_not_sg_rule - Security Groups related to the instance (without including primary network interface) not containing the specified rule
	- has_invalid_ami - Instances using invalid AMI
- lc
	- has_invalid_ami - LC using invalid AMI
- all resources
	- connected - resource on left side is connected to the resources on the right side of the rule, e.g. `vpc.connected(resource=["igw"])`
	- unconnected - resource on left side is not connected to the resources on the right side of the rule


#### Examples
- instance.has_sg_rule(ipPermissions.fromPort=80)
- instance.has_not_sg_rule(ipPermissions.fromPort=22)
- vpc.connected(resource=["igw", "cgw"])
- subnet.unconnected(resource=["instance"])
- instance.has_invalid_ami()
- lc.has_invalid_ami()