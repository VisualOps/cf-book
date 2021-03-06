# Resource attributes
The attributes CloudFielder supports are the same as [AWS](http://aws.amazon.com/documentation/). Because different SDKs have different attribute names, CloudFielder uses the XML return values of the AWS API as standard attributes.

#### For exmaple: [eip](http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeAddresses.html)
![](https://raw.githubusercontent.com/VisualOps/cf-book/master/images/resource_attributes_eip.png)

#### Different level attribute
	
	acl(assocaitionSet.subnetId = "subnet-12345678")

	or

	acl(assocaitionSet["subnetId"] = "subnet-12345678")

#### Multiple attributes

	acl(associationSet.subnetId = "subnet-12345678", tagSet["Name"] = "public")

#### Multiple attributes at second level
	
	# find acl with one association containing subnet-12345678 and acl-12345678
	acl(associationSet = {"subnetId": "subnet-12345678", "networkAclId":"acl-12345678"})
	
	!=
	
	# find acl with all associations containing subnet-12345678 and acl-12345678
	acl(associationSet.subnetId = "subnet-12345678", associationSet.networkAclId=acl-12345678"})

- ## region
	- regionName

- ## vpc
	- cidrBlock
	- dhcpOptionsId
	- state
	- vpcId
	- instanceTenancy
	- isDefault
	- tagSet
	- regionName

- ## acl
	- associationSet
		- subnetId
		- networkAclId
		- networkAclAssociationId
	- entrrySet
		- protocol
		- egress
		- ruleNumber
		- cidrBlock
		- ruleAction
	- isDefault
	- networkAclId
	- tagSet
	- vpcId
	- regionName

- ## rtb
	- associationSet
		- routeTableAssociationId
		- main
		- routeTableId
	- propagatingVgws
	- routeTableId
	- routeSet
		- origin
		- destinationCidrBlock
		- networkInterfaceId
		- state
	- tagSet
	- vpcId
	- regionName

- ## subnet
	- availabilityZone
	- mapPublicIpOnLaunch
	- avaliableIpAddressCount
	- defaultForAz
	- cidrBlock
	- state
	- vpcId
	- tagSet
	- subnetId
	- regionName

- ## instance
	- amiLaunchIndex
	- imageId
	- instanceId
	- instanceType
	- kernalId
	- keyName
	- launchTime
	- monitoring
		- state
	- placement
		- gourpName
		- tenancy
		- availabilityZone
	- platform
	- privateIpAddress
	- privateDnsName
	- productCodes
	- dnsName
	- ipAddress
	- ramdiskId
	- instanceState
		- code
		- name
	- stateTransitionReason
	- subnetId
	- vpcId
	- architecture
	- blockDeviceMapping
		- deviceName
		- ebs
			- status
			- deleteOnTermination
			- volumeId
			- attachTime
	- networkInterfaceSet
		- status
		- macAddress
		- sourceDestCheck
		- vpcId
		- description
		- networkInterfaceId
		- privateIpAddress
		- groupSet
			- groupName
			- groupId
		- attachment
			- status
			- deviceIndex
			- deleteOnTermination
			- attachmentId
			- attachTime
		- subnetId
		- ownerId
		- privateIpAddressSet
			- privateIpAddress
			- primary
			- association
				- publicIp
				- publicDnsName
				- ipOwnerId
		- association
			- publicIp
			- publicDnsName
			- ipOwnerId
	- clientToken
	- ebsOptimized
	- hypervisor
	- iamInstanceProfile
	- instanceLifecycle
	- rootDeviceName
	- rootDeviceType	
	- groupSet
		- groupName
		- groupId
	- sourceDestCheck
	- spotInstanceRequestId
	- sriovNetSupport
	- reason
	- tagSet
	- virtualizationType
	- regionName

- ##eni
	- attachment
			- status
			- deviceIndex
			- deleteOnTermination
			- attachmentId
			- attachTime
			- instanceId
			- instanceOwnerId
	- association
			- publicIp
			- publicDnsName
			- ipOwnerId
	- groupSet
		- groupName
		- groupId
	- association
	- availabilityZone
	- description
	- macAddress
	- networkInterfaceId
	- ownerId
	- privateIpAddress
	- privateDnsName
	- privateIpAddressSet
		- primary
		- privateIpAddress
	- requestrManaged
	- sourceDestCheck
	- status
	- subnetId
	- tagSet
	- vpcId	
	- regionName

- ##sg
	- groupDescription
	- groupName
	- ipPermissions
		- toPort
		- fromPort
		- ipRanges
			- cidrIp
		- groups
			- groupName
			- groupId
			- userId
		- ipProtocol
	- ownerId
	- groupId
	- ipPermissionEgress
	- tagSet
	- vpcId
	- regionName

- ##eip
	
	- instanceId
	- publicIp
	- allocationId
	- domain
	- associationId
	- networkInterfaceId
	- networkInterfaceOwnerId
	- privateIpAddress
	- regionName

- ##vol
	- attachmentSet
		- status
		- attachTime
		- instanceId
		- volumeId
		- deleteOnTermination
		- device
	- avaliabilityZone
	- createTime
	- encrypted
	- kmsKeyId
	- size
	- snapshotId
	- status
	- volumeId
	- iops
	- tagSet
	- volumeType
	- regionName

- ##igw
	- attachmentSet
		- vpcId
		- state
	- internetGatewayId
	- tagSet
	- regionName

- ##vgw
	- availabilityZone
	- state
	- type
	- attachments
		- vpcId
		- state
	- vpnGatewayId
	- tagSet
	- regionName

- ##vpn
	- customerGatewayId
	- state
	- type
	- vpnConnectionId
	- vpnGatewayId
	- options
		- staticRoutesOnly
	- routes
		- destinationCidrBlock
		- state
	- tagSet
	- vgwTelemetry
		- status
		- acceptedRouteCount
		- outsideIpAddress
		- lastStatusChange
		- statusMessage
	- regionName

- ##cgw
	- ipAddress
	- bgpAsn
	- customerGatewayId
	- state
	- type
	- tagSet
	- regionName


- ##elb
	- AvailabilityZones
	- BackendServerDescriptions
	- CanonicalHostedZoneName
	- CanonicalHostedZoneNameID
	- CreatedTime
	- DNSName
	- HealthCheck
		- HealthyThreshold
		- Interval
		- Target
		- Timeout
		- UnhealthyThreshold
	- Instances
		- InstanceId
	- ListenerDescriptions
		- Listener
			- InstancePort
			- LoadBalancerPort
			- Protocol
			- InstanceProtocol
			- SSLCertificateId
		- PolicyNames
			- member

	- LoadBalancerName
	- Policies
		- LBCookieStickinessPolicies
		- AppCookieStickinessPolicies
		- OtherPolicies
			- member
	- Scheme
	- SecurityGroups
		- member
	- SourceSecurityGroup
		- GroupName
		- OwnerAlias
	- Subnets
	- VPCId
	- regionName

- ## asg
	- AutoScalingGroupARN
	- AutoScalingGroupName
	- AvailabilityZones
	- CreatedTime
	- DefaultCooldown
	- DesiredCapacity
	- EnabledMetrics
	- HealthCheckGracePeriod
	- HealthCheckType
	- Instances
		- InstanceId
		- AvailabilityZone
		- HealthStatus
		- LifecycleState
		- LaunchConfigurationName
	- MaxSize
	- LaunchConfigurationName
	- LoadBalancerNames
	- MinSize
	- PlacementGroup
	- Status
	- SuspendedProcesses
	- Tags
	- TerminationPolicies
	- VPCZoneIdentifier
	- regionName

- ## lc
	- AssociatePublicIpAddress
	- BlockDeviceMappings
		- DeviceName
		- Ebs
			- SnapshotId
			- VolumeSize
			- VolumeType
	- ClassicLinkVPCId
	- ClassicLinkVPCSecurityGroups
	- CreatedTime
	- EbsOptimized
	- IamInstanceProfile
	- ImageId
	- InstanceMonitoring
		- Enabled
	- InstanceType
	- KernelId
	- KeyName
	- LaunchConfigurationARN
	- LaunchConfigurationName
	- PlacementTenancy
	- RamdiskId
	- SecurityGroups
		- member
	- SpotPrice
	- UserData
	- regionName

- ## dbinstance
	- AllocatedStorage
	- AutoMinorVersionUpgrade
	- AvailabilityZone
	- BackupRetentionPeriod
	- CACertificateIdentifier
	- CharacterSetName
	- DBInstanceClass
	- DBInstanceIdentifier
	- DBInstanceStatus
	- DBName
	- DBParameterGroups
		- DBParameterGroup
			- DBParameterGroupName
			- ParameterApplyStatus
	- DBSecurityGroups
	- DBSubnetGroup
		- Subnets
			- Subnet
				- SubnetStatus
				- SubnetIdentifier
				- SubnetAvailabilityZone
					- Name
					- ProvisionedIopsCapable
		- DBSubnetGroupName
		- VpcId
		- DBSubnetGroupDescription
		- SubnetGroupStatus

	- DbiResourceId
	- Endpoint
		- Port
		- Address
	- Engine
	- EngineVersion
	- InstanceCreateTime
	- Iops
	- KmsKeyId
	- LatestRestorableTime
	- LicenseModel
	- MasterUsername
	- MultiAZ
	- OptionGroupMemberships
		- OptionGroupMembership
			- Status
			- OptionGroupName
	- PendingModifiedValues
	- PreferredBackupWindow
	- PreferredMaintenanceWindow
	- PublicyAccessible
	- ReadReplicaDBInstanceIdentifier
	- ReadReplicaSourceDBInstanceIdentifier
	- SecondaryAvailabilityZone
	- StatusInfos
	- StorageEncrypted
	- StorageType
	- TdeCredentialArn
	- VpcSecurityGroups
		- Status
		- VpcSecurityGroupId
	- regionName


- ## dbsubnetgroup
	- DBSubnetGroupDescription
	- DBSubnetGroupName
	- SubnetGroupStatus
	- Subnets
		- Subnet
			- SubnetStatus
			- SubnetIdentifier
			- SubnetAvailabilityZone
				- Name
				- ProvisionedIopsCapable
	- VpcId
	- regionName