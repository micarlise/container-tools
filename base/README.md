## build base container

```
docker build -t micarlise/container-tools:base .
```

### push to docker hub

```
docker push micarlise/container-tools:base
```

## Quick Use

### Run as a shell container

Remember to add target networks or namespaces if connecting to other
container/pods.

**Docker**
```
docker run -it micarlise/container-tools:base
```

* --net=<target_network>

**Kubernetes**
```
kubectl run test-shell --rm -i --tty -image micarlise/container-tools:base -- bash
```

* --env="POD_NAMESPACE=<target_namespace>"

### Use wait-for-it as a docker setup container

Example creates a "titles" index on an elasticsearch instance, but waits for the elasticsearch service to be up.

```
setup_es
  image: micarlise/container-tools:base
  depends_on:
    - elasticsearch
  restart: "no"
  command: ["wait-for-it.sh", "elasticsearch:9200", "--", "curl", "-X", "PUT", "elasticsearch:9200/titles"]
```
