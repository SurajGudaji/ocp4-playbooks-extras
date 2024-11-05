ocp-cluster-observability-operator
=========

This role is used to validate operator development using operator-sdk.

Requirements
------------

- OCP 4.x healthy cluster on PowerVS.


Role Variables
--------------

| Variable                                   | Required | Default                                                                              | Comments                                                                                                                       |
|--------------------------------------------|----------|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| op_api_role_enable                            | no       | false                                                                                | Set it to true to run this playbook                                                                                            |
| op_cleanup                            | no       | false                                                                                | Set it to true to do operator cleanup.                                                                                            |
| build_operator_image                   | no       | true                                                                                 | Set it to true to build the operator image                                                                      |
| deploy_operator               | no       | false                                                                                 | Set it to true to deploy the operators                                                                            |
| OPERATOR_SDK_VERSION                    | no       | "1.37.0"                                                                               | Version of operator-sdk to be installed.                                                                                                       |
| op_api_dir                      | no       | "/tmp/operator-api"                                                                    | Directory where the operator workspace are intialized.                                                                                                         |
| ocp_version                | yes       |  | Openshift version on which this validation is run |
| quay_username                    | yes       |                                                                                | quay account username where the operator images will be pushed                                                                                                       |




Dependencies
------------

- Login to a quay.io account
```
docker login -u='' -p='' quay.io
```

Example Playbook
----------------

```
---
- name: Validate Operator development and installation
  hosts: bastion
  tasks:
    - name: Validate Operator development and installation
      include_role:
        name: ocp-operator-api
```


License
-------

See LICENCE.txt

Author Information
------------------

Suraj.Gudaji1@ibm.com
