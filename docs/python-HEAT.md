# Recipe for Python bindings 

<span style="color:red"> This documentation is under development. </span>

## Environment setup 

Download the repository for the [DODAS-CMS cluster deployment](https://github.com/indigo-dc/mesos-cluster/tree/master/deploy/openstack-heat/dodas) and enter in `deploy/openstack-heat`:

```bash
git clone https://github.com/indigo-dc/mesos-cluster
cd mesos-cluster/deploy/openstack-heat/dodas
```

Install the dependencies with `pip` or use `pipenv` to create a virtual environment for this deployment:

```bash
sudo pip install -r requirements.txt
```

OR

```bash
pipenv install
pipenv shell
```

The dependencies installed include [the HEAT client python bindings](https://docs.openstack.org/python-heatclient/latest/index.html). 

> **NOTES**: You can also install dependencies using the package manager of your system; e.g. on ubuntu you can do: 
> ```bash
> sudo apt install python-heatclient ...
> ```
> For other operating systems you can look at the openstack documentation.


## DODAS site configuration 

Once the environment setup is ready you need to prepare a JSON based configuration file and finally start the execution. 

* Copy the heat environment JSON and the setup config from the templates (`env_heat.json_template`, `setup_config.json_template`) inside the `dodas` folder:

```bash
cp env_heat.json_template env_heat.json
cp setup_config.json_template setup_config.json
```

* the `env_heat.json` file will appear as the following. You have now to configure it as your needs. You can find a reference for each parameter [here](config-ref-HEAT.md).

```JSON
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

* the `setup_config.json` file will appear as the following. You have now to configure it as your needs. You can find a reference for each parameter [here](config-ref-python-script.md).

```JSON
{
    "openstack_auth_url": "",
    "openstack_project_id": "",
    "openstack_user": "",
    "heat_template": "mesoscluster-cms.yaml",
    "heat_environment_variables": "env_heat.json",
    "setup_script": "../setup.sh",
    "stack_name": "",
    "indigo": {
        "client_id": "",
        "client_secret": "",
        "grant_type": "password",
        "username": "",
        "scope": "openid profile email offline_access",
        "url": "https://iam-test.indigo-datacloud.eu/token"
    }
}
```

## Cluster creation

Starting the deployment is possible executing:

```bash
python setup_cluster_dev.py setup_config.json run
```

You'll be prompted with messages asking for OpenStack keystone password and INDIGO password. Insert them and you are done, the deployment will start after that.

## Deployment monitor

Once the deployment process started, it is possible to monitor it through the OpenStack web interface as follows:

```bash
python setup_cluster_dev.py setup_config.json status
```

If you want to monitor the creation activity you can use the status command as follow:

```bash
python setup_cluster_dev.py setup_config.json status --monitor=True
```

This will monitor the creation process giving you the current status until the end of the operation or the press of `^C` keyboard sequence.

Another option is to use the *Horizon* portal as following:

* after logging in with your user name go to the project that you indicated in the `setup_cluster.py` few steps above
* click the tab `ORCHESTRATION` followed by `Stacks`
* now you should be able to see you deployment under the very same name you inserted when prompted by the `setup_cluster.py` script. The status of the deployment is also shown on the same line
* you can click on the the deployment to gather more in-depth information

In alternative, for more advanced uses, you can use python bindings in order to debug and monitor the deployment. You can find an example script [here](https://gist.githubusercontent.com/dciangot/054f0d93598a670399c0b5bd36f4fd6d/raw/a86bad8cfe2905b5ee053635ae6add37b2e73381/deployment_status.py)

## Cluster deletion

Delete the cluster with the following command and wait for the process to be completed:

```bash
python setup_cluster_dev.py setup_config.json delete
```
