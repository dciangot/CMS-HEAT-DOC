# HEAT-based deployment
<span style="color:red"> This documentation is under development. </span>
## Prerequisites
Here we need to provide all the DODAS requirements for OpenStack (HEAT). 
In order to run the HEAT-based toolkit you need:

* To be granted with a keystone access 
* To be authorized for accessing a project
* The project must have at least one private network with outbound connectivity
* The project must have access to either Ubuntu 14.04 or 16.04 server image with hooks for HEAT.
    * Get the images here:
        * [Ubuntu 14.04](https://cernbox.cern.ch/index.php/s/I9G2mW7Gymrh8wZ/download)
        * [Ubuntu 16.04](https://cernbox.cern.ch/index.php/s/yNxOulSmebMDKAZ/download)
             
## Recipes for deployment 
This guide provides step by step deployment recipes with two different HEAT interfaces. You can find below the links to the instructions for setup with the HEAT client python bindings and the command line interface.
1. [Python bindings](python-HEAT.md)
2. [Command Line Interface](IM.md)
