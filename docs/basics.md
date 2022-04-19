## Basic info commands

* `kubectl version` - Check the version of the local kubectl tool and the Kubernetes API server.
* `kubectl get componentstatuses` - Check the general health of your cluster.
* `kubectl get nodes` - List kubernetes worker nodes
* `kubectl describe nodes <node>` - Get a lot of information about a specific node.

## Namespaces
* `kubectl --namespace=mystuff` - References objects in the mystuff namespace.

## Contexts

* `kubectl config set-context my-context --namespace=mystuff` - Create a context with a different default namespace.
* `kubectl config set-context other-cluster --cluster=cluster_nickname` - Create a context for a specific cluster.
* `kubectl config use-context my-context` - Use context.
