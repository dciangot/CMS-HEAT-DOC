# Recipe for Python bindings 
<span style="color:red"> This documentation is under development. </span>

## Environment setup 
Before running the recipe you need to setup the environment by installing [the HEAT client python bindings](https://docs.openstack.org/python-heatclient/latest/index.html). Using pip: 
```
pip install heatclient
```
Then you have to download the repository for the [DODAS-CMS cluster deployment](https://github.com/indigo-dc/mesos-cluster/tree/master/deploy/openstack-heat/dodas):
```
git clone https://github.com/indigo-dc/mesos-cluster
```
## DODAS site configuration 
Once the environment setup is ready you need to prepare a JSON based configuration file and finally start the execution. 

* get to the deployment directory and copy the heat environment JSON from the template `env_heat.json_template`
```
cd mesos-cluster/deploy/openstack-heat/dodas
cp env_heat.json_template env_heat.json
```

* the `env_heat.json` file will appear as the following. You have now to configure it as your needs. You can find a reference for each parameter [here](config-ref-HEAT.md).
```
{
    "parameters": {
        "network": "",
        "ssh_key_name": "",
        "master_flavor": "",
        "loadbalancer_flavor": "",
        "slave_flavor": "",
        "marathon_username": "",
        "marathon_password": "",
        "number_of_slaves": 4,
        "number_of_masters": 1,
        "server_image": "",
        "cms_wn_image": "spiga/cmswn",
        "cms_proxycache_image": "spiga/ttscache",
        "iam_token": "",
        "iam_client_id": "",
        "iam_client_secret": "",
        "cms_local_site": "",
        "cms_stageoutsite": "",
        "cms_stageoutserver": "",
        "cms_stageoutprefix": "",
        "monitor_ip": "",
        "elasticsearch_secret": ""
    }
}
```

## Cluster creation
Starting the deployment is possible following the next steps:
* you have to change the following parameters in the setup script `setup_cluster.py`:
    * AUTH_URL: your keystone URL endpoint of the openstack instance
    * PROJECT_ID: your openstack project ID


* executing `python dodas/setup_cluster.py` you'll be prompted with messages asking for OpenStack keystone username and password, and the stack deployment name. Insert them and you are done, the deployment will start after that.

## Deployment monitor
Once the deployment process started, it is possible to monitor it through the OpenStack web interface as follows:

* after logging in with your user name go to the project that you indicated in the `setup_cluster.py` few steps above
* click the tab `ORCHESTRATION` followed by `Stacks`
* now you should be able to see you deployment under the very same name you inserted when prompted by the `setup_cluster.py` script. The status of the deployment is also shown on the same line
* you can click on the the deployment to gather more in-depth information

In alternative, for more advanced uses, you can use python bindings in order to debug and monitor the deployment. You can find an example script [here](https://gist.githubusercontent.com/dciangot/054f0d93598a670399c0b5bd36f4fd6d/raw/a86bad8cfe2905b5ee053635ae6add37b2e73381/deployment_status.py)

