# HOW TO...

## Debug deployment

<span style="color:red"> This documentation is under development. </span>


### Python script

Debug the cluster creation through the script using the command `debug` (read about the Python script installation [here](python-HEAT.md)). This command accept other parameters to help your debugging: you can debug `resources` or `softwares` and for each one you can see the current status and the status reason in case of errors (with the std input and output too).

Here some example of the possible commands:

```bash
# Get all resources status
python setup_cluster_dev.py setup_config.json debug resources all
# Get only resources that have failed
python setup_cluster_dev.py setup_config.json debug resources
python setup_cluster_dev.py setup_config.json debug resources fails

# Get all softwares status
python setup_cluster_dev.py setup_config.json debug softwares all
# Get only softwares that have failed
python setup_cluster_dev.py setup_config.json debug softwares
python setup_cluster_dev.py setup_config.json debug softwares fails
# Get details on software with ID=abc
python setup_cluster_dev.py setup_config.json debug softwares abc
```

TBD
