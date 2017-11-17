# HEAT-based deployment
<span style="color:red"> This documentation is under development. </span>
## Prerequisites
Here we need to provide all the DODAS requirements for OpenStack (HEAT). 
In order to run the HEAT-based toolkit you need:

* To be granted with a keystone access 
* To be authorized for accessing a project
* The project has to ...  one private network with outbound connectivity
* The project must have access to either Ubuntu 14.04 or 16.04 server image with hook for HEAT.
    * Get images here:
        * [Ubuntu 14.04](https://LinkHERE) 
        * [Ubuntu 16.04](https://cernbox.cern.ch/index.php/s/yNxOulSmebMDKAZ/download)
             
## Recipes for deployment 
This guide provides step by step recipes both for Python bindings usage and direct HEAT command line interface. Below direct links to the related documentation: 
* [Python bindings](python-HEAT.md)
* [HEAT Command Line ](IM.md)