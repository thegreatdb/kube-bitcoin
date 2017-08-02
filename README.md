# kube-bitcoin

Runs a bitcoin full node in a kubernetes cluster.


## Prerequisites

First provision a disk:

```console
  gcloud compute disks create --size=300GB bitcoin-data
```

Next create a secret file from the template:

```console
  cp deploy/bitcoin-secret.yml.template deploy/bitcoin-secret.yml
```

Then find the base64 encoding of the username and password you want to use:

```console
  echo -n YOURUSERNAME | base64
  echo -n YOURPASSWORD | base64
```

Fill in those values in the `bitcoin-secret.yml` file.

Finally create the kubernetes resources:

```console
  kubectl create -f deploy/
```
