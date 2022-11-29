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