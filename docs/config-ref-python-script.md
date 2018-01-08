# Python setup cluster script reference

<span style="color:red"> This documentation is under development. </span>
## Reference guide

### Generals

* **openstack_auth_url** *(string, default='')*: openstack auth entrypoint

* **openstack_project_id** *(string, default='')*: openstack project identifier

* **openstack_user** *(string, default='')*: openstack username

* **heat_template** *(string, default='mesoscluster-cms.yaml')*: name of the HEAT file

* **heat\_environment\_variables** *(string, default='env_heat.json')*: name of the HEAT environment file

* **marathon_password** *(string, default='password')*: password for marathon instance

* **stack-name** *(string, default='')*: name to assign to the stack

* **files** *(string, default='{} or key not present')*: a dictionary where you can specify a local file to load inside the HEAT template. The key will be the name of the file in the HEAT template and the value will be the path to the local file that have to be loaded.

### INDIGO

* **client_id** *(string, default='')*: INDIGO user identifier

* **client_secret** *(string, default='')*: INDIGO user secret

* **grant_type** *(string, default='password')*: INDIGO access type

* **username** *(string, default='')*: INDIGO username

* **scope** *(string, default='openid profile email offline_access')*: access type

* **url** *(string, default='https://iam-test.indigo-datacloud.eu/token')*: URL of INDIGO token service
