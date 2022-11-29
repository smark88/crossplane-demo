# crossplane-demo
Create resources using crosplane

## Overview 
create indivdual resources and recreate the same resources using Composition (XR) and CompositeResourceDefinition(XRD)

## Example 
Create vpc sg and sgr
```
.
└── vpc-sg-sgr
    ├── composition -- Composition (XR) and CompositeResourceDefinition(XRD) 
    │   ├── composition.yaml -- contains all direct yamls
    │   ├── definition.yaml -- vars
    │   └── instances
    │       └── deploy.yaml
    └── direct --  Calls directly to crossplane apis
        ├── sg.yaml
        ├── sg_rule.yaml
        └── vpc.yaml
```
#### results
```
❯ k get vpc,SecurityGroup,SecurityGroupRule
NAME                                                            READY   SYNCED   ID                      CIDR          IPV6CIDR   AGE
vpc.ec2.aws.crossplane.io/smark-test-vpc-wg8fl                  True    True     vpc-02527e103fe1fc04a   10.8.0.0/16              18m

NAME                                                            READY   SYNCED   ID                     VPC                     AGE
securitygroup.ec2.aws.crossplane.io/smark-test-vpc-w2lzd        True    True     sg-0692187a977671f06   vpc-02527e103fe1fc04a   15m

  NAME                                                          READY   SYNCED   ID                      SG
securitygrouprule.ec2.aws.crossplane.io/smark-test-vpc-r7klp    True    True     sgr-06f5d3ceaeed364f3   sg-0692187a977671f06
```