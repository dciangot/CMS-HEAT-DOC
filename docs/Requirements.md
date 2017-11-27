# General Requirements
<span style="color:red"> This documentation is under development. </span>

Describe here user requirements to deploy CMS site with DODAS 

* Register a user to the IAM.
* Register a client on IAM server, self service registration are supported [here](https://iam-test.indigo-datacloud.eu/login). 
* [curl](https://curl.haxx.se/download.html) and [jq](https://stedolan.github.io/jq/) installed on the system
* Get a IAM token: it can be retrieved with [get_token.sh](https://gist.githubusercontent.com/dciangot/3b098173fc1710ad6b07ecda5b4e179a/raw/379949e1ce00d28dbdb64b65ed3a1d1676da4789/get_token.sh) or running the following command:

```
curl -s -L \
 -d client_id="CHANGEME" \
 -d client_secret="CHANGEME" \ 
 -d grant_type=password \
 -d username="CHANGEME" \
 -d password="CHANGEME" \
 -d scope="openid profile email offline_access" \
  https://iam-test.indigo-datacloud.eu/token | jq -r .access_token
```
