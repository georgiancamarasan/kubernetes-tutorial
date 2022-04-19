## Create a ConfigMap using an environment file

* `kubectl create configmap <config-name> --from-env-file=config.txt` - Creates a config map using a key=value pairs file, like the one below:

## Environment config file
    prop1=value1
    prop2=value2
