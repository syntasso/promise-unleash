# Unleash

> **Warning**
>
> **To use this Promise, the Kubernetes cluster running Kratix must be registered
as a Worker Cluster**
>
> Check out the [Compound Promises
guide](https://kratix.io/docs/main/guides/compound-promises) on the Kratix
documentation for details on how to setup your platform.

This Promise provides Unleash-as-a-Service. The Promise has 1 fields:
* `.spec.autoscaling` which can be set to `true` or `false`

Unleash needs a database to run. This Promise creates a database using the Kratix Marketplace PostgreSQL Promise.

To install:
```
kubectl apply --context kind-platform -f https://raw.githubusercontent.com/syntasso/promise-unleash/main/promise.yaml
```

To make a resource request:
```
kubectl apply --context kind-platform -f https://raw.githubusercontent.com/syntasso/promise-unleash/main/resource-request.yaml
```

The request above will create a Unleash and a PostreSQL instance in a dedicated namespace.

## Accessing Unleash

To access your Unleash instance, run in your worker cluster:

```bash
# Replace <example-unleash> with the correct namespace
kubectl port-forward --context kind-worker -n example-unleash svc/example-unleash 4242
```

Go to http://localhost:4242. The default credentials are provided in the Promise status field or available below:

* username: admin
* password: unleash4all

## Development

For development see [README.md](./internal/README.md)

## Questions? Feedback?

We are always looking for ways to improve Kratix and the Marketplace. If you
run into issues or have ideas for us, please let us know. Feel free to [open an
issue](https://github.com/syntasso/kratix-marketplace/issues/new/choose) or
[put time on our calendar](https://www.syntasso.io/contact-us). We'd love to
hear from you.
