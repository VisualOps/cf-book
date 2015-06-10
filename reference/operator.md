# Operator

The operators can be used in expression are as follow:

- `>`
- `>=`
- `<=`
- `<`
- `=`
- `!=`
- `like`
- `not like`
- `in`
- `not in`
- `has`
- `has not`

Different operator should be used with corresponding type

`Num` < | > | >= | <= `Num`

`Array` has | has not `Array`

`Str` like | not like `Str`

`Str`|`Num`|`Dict` in | not in `Array`

`All` = | != `All`

#### Notice

If `attr != ""` or `attr != null` is specified, you will filter the resources having the attribute `attr` and a valid value.

- sg(vpcId != ""): SG belonging to VPC
- sg(vpcId = ""): SG belonging to EC2 classic

#### Examples

- instance(tags["Name"] = "db")
- instance(tags["Name"] != "db")
- instance(tags["Name"] like "^db$")
- instance(tags["Name"] in ["db", "web"])
- elb(AvailabilityZones has ["us-east-1a","us-east-1b"])
- sg(ipPermissions = {"fromPort":80,  "ipProtocol":"tcp"},  ipPermissions = {"fromPort":22,  "ipProtocol":"tcp"})
- sg(ipPermissions.fromPort > 10000)