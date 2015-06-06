# Operator

The operators can be use in expression are as follow:

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
If use `attr != ""` or `attr != null`, you can filter the resource has attribute `attr` and have valid value.

- sg(vpcId != ""): sg that belong to vpc
- sg(vpcId = ""): sg that belong to EC2 classic

#### Example

- instance(tags["Name"] = "db")
- instance(tags["Name"] != "db")
- instance(tags["Name"] like "^db$")
- instance(tags["Name"] in ["db", "web"])
- elb(AvailabilityZones has ["us-east-1a","us-east-1b"])
- sg(ipPermissions = {"fromPort":80,  "ipProtocol":"tcp"},  ipPermissions = {"fromPort":22,  "ipProtocol":"tcp"})
- sg(ipPermissions.fromPort > 10000)