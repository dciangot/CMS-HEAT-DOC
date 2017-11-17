# HEAT environment configuration reference

<span style="color:red"> This documentation is under development. </span>
## Reference guide

### Mandatory fields

* *network (string, default='')*: openstack network identifier

* *ssh_key_name (string, default='')*: ssh key pair identifier

* *master_flavor (string, default='')*: openstack flavor identifier for mesos master nodes

* *loadbalancer_flavor (string, default='')*: openstack flavor identifier for loadbalancer

* *slave_flavor (string, default='')*: openstack flavor identifier for mesos save nodes

* *marathon_username (string, default='admin')*: username for marathon instance

* *marathon_password (string, default='password')*: password for marathon instance

* *number of slaves (int, default=2)*: number of slave nodes

* *number of masters (int, default=1)*: number of master nodes

* *server_image (string, default='')*: openstack image identifier to be used for all the created VMs

* *cms_wn_image (string, default='')*: docker image identifier for WNs, suggested one at this stage is spiga/cmswn

* *cms_proxycache_image (string, default='')*: docker image for proxy cache application, suggested spiga/ttscache

* *iam_token (string, default='')*: token of the IAM client retrieved as in prerequisites [here](Getting-started.md)

* *iam_client_id (string, default='')*: IAM client ID

* *iam_client_secret (string, default='')*: IAM client secret

* *cms_local_site (string, default='')*: identifier of the CMS site shown to the htcondor pool, at the moment the mandatory form is `T3_Opportunistic_<sitename choosen>`

### Optional fields

* *cms_stageoutsite (string)*:

* *cms_stageoutserver (string)*:

* *cms_stageoutprefix (string)*:

* *monitor_ip (string)*:

* *elasticsearch_secret (string)*:
