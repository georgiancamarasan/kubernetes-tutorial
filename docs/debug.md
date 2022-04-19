## Debugging commands

* `kubectl logs <pod-name>` - lists the current logs.
* `kubectl logs <pod-name> -c container name` - lists the current logs from a container. Use this if you have multiple containers in the same pod.
* `kubectl exec -it <pod-name> -- bash` - Will provide an interactive shell.
* `kubectl attach -it <pod-name>` - Will attach to the running process and allow you to send input to it, if it accepts any.
* `kubectl cp <pod-name>:</path/to/remote/file> </path/to/local/file>` - Copy a file from a running container to your local machine.
* `kubectl port-forward <pod-name> 8080:80` - Forwards traffic from the local machine on port 8080 to the remote container on port 80.
* `kubectl port-forward services/<service-name> 8080:80` - Forwards traffic from the local machine on port 8080 to the service on port 80.

