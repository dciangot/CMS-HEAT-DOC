## Python requirements

* install [the HEAT client python bindings](https://docs.openstack.org/python-heatclient/latest/index.html): 
```
pip install heatclient
```

* get the repository for the [DODAS-CMS cluster deployment](https://github.com/indigo-dc/mesos-cluster/):
```
git clone https://github.com/indigo-dc/mesos-cluster
```

## Cluster configuration 
* get the repository for the [DODAS-CMS cluster deployment](https://github.com/indigo-dc/mesos-cluster/):
```
git clone https://github.com/indigo-dc/mesos-cluster
```

* get to the deployment directory and copy the heat environment json from `dodas/env_heat.json_template`
```
cd mesos-cluster/deploy/openstack-heat
cp dodas/env_heat.json_template env_heat.json
cp dodas/mesoscluster-cms.yaml .
```

* the `env_heat.json` file will appear as the following. You can configure it as your needs. You can also find a reference for each parameter [here](config-ref-HEAT.md).
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

* in order to setup using the script you have to provide some parameters in `dodas/setup_cluster.py`:
    * AUTH_URL: the keystone URL endpoint of the openstack instance
    * PROJECT_ID: the openstack project ID

* executing `python dodas/setup_cluster.py` you'll be prompted with messages asking for openstack username and password. Insert them and the deployment of the cluster will start after that.

N.B. there is no support in this script for federated credentials yet
 
## Deployment monitor

* An example on how to use python binding for heatclient for deployment debug and monitoring is [here](https://gist.githubusercontent.com/dciangot/054f0d93598a670399c0b5bd36f4fd6d/raw/a86bad8cfe2905b5ee053635ae6add37b2e73381/deployment_status.py)

* TODO: link a heatclient reference
