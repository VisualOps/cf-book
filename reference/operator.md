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

#### Example

- instance(tags["Name"] = "db")
- instance(tags["Name"] != "db")
- instance(tags["Name"] like "^db$")
- instance(tags["Name"] in ["db", "web"])
- elb(AvailabilityZones has not ["us-east-1a","us-east-1b"])