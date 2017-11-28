# Python setup cluster script reference

<span style="color:red"> This documentation is under development. </span>
## Reference guide

### Generals

* **auth_url** *(string, default='')*: openstack auth entrypoint

* **project_id** *(string, default='')*: openstack project identifier

* **user** *(string, default='')*: openstack username

* **heat_template** *(string, default='mesoscluster-cms.yaml')*: name of the heat file

* **heat\_environment\_variables** *(string, default='env_heat.json')*: name of the heat environment file

* **setup_script** *(string, default='setup.sh')*: name of the setup file

* **marathon_password** *(string, default='password')*: password for marathon instance

* **stack-name** (string, default='')*: name to assign to the stack

### INDIGO

* **client_id** *(string, default='')*: INDIGO user identifier

* **client_secret** *(string, default='')*: INDIGO user secret

* **grant_type** *(string, default='password')*: INDIGO access type

* **username** *(string, default='')*: INDIGO username

* **scope** *(string, default='openid profile email offline_access')*: access type

* **url** *(string, default='https://iam-test.indigo-datacloud.eu/token')*: URL of INDIGO token service
