# HEAT-based deployment
<span style="color:red"> This documentation is under development. </span>
## Prerequisites

In order to run the HEAT-based deployments you need:

* openstack requirements:

    * local access to a tenant
    
    * at least one private network with outbound connectivity

    * import an HEAT Ubuntu (16 or 14) server server image in the openstack tenant
        * you can get the HEAT Ubuntu16 one [here](https://cernbox.cern.ch/index.php/s/yNxOulSmebMDKAZ/download)
    
## Deployment tools

* [Python bindings](python-HEAT.md)
* [HEAT CLI](IM.md)