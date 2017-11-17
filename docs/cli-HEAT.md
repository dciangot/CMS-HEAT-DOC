# Recipe for CLI

<span style="color:red"> This documentation is under development. </span>

## Environment setup 
Before running the recipe you need to setup the environment by installing [the HEAT client python bindings](https://docs.openstack.org/python-heatclient/latest/index.html). Using pip: 
```
pip install heatclient
```

Then download the environment and configuration templates as follows:
```
wget https://gist.githubusercontent.com/dciangot/b32bf0a84bc4d7ab761452ec7a2d9815/raw/c0e9417ffc1a9af3805cca5a3c7b7a2a6694fc87/env.sh
wget https://gist.githubusercontent.com/dciangot/13ca8b08f2afafdd7ac81d0e3e549cdc/raw/8b55b1e272976cf29e7dd4e044814fabb1638091/env_heat
```

## DODAS site configuration

* Set all the requested information in the file `env.sh`

* Change the configuration (`env_heat` file) as you need. You can find a reference for each parameter [here](config-ref-HEAT.md).


## Cluster creation
Starting the deployment is possible following the next steps:

* Setup the enviroment:
```
source env.sh
```

* Start the deployment:
```
heat stack-create <YOUR_CLUSTER_NAME> -e env_heat --template-url "https://raw.githubusercontent.com/indigo-dc/mesos-cluster/master/deploy/openstack-heat/dodas/mesoscluster-cms.yaml"
```

## Deployment monitor
Once the deployment process started, it is possible to monitor it through the OpenStack web interface as follows:

* after logging in with your user name go to the project that you indicated in the `setup_cluster.py` few steps above
* click the tab `ORCHESTRATION` followed by `Stacks`
* now you should be able to see you deployment under the very same name you inserted when prompted by the `setup_cluster.py` script. The status of the deployment is also shown on the same line
* you can click on the the deployment to gather more in-depth information

In alternative, for more advanced usages, you can explore the [CLI tools](https://docs.openstack.org/python-heatclient/latest/man/heat.html). For example you can get the list of current stacks with the corresponding status as follow:

````
heat stack-list
````