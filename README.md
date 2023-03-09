# Unleash

This Promise provides Unleash-as-a-Service. The Promise has 1 fields:
* `.spec.autoscaling`

Check the CRD documentation for more information.


To install:
```
kubectl apply -f https://raw.githubusercontent.com/syntasso/promise-unleash/main/promise.yaml
```

To make a resource request:
```
kubectl apply -f https://raw.githubusercontent.com/syntasso/promise-unleash/main/resource-request.yaml
```

## Accessing Unleash

To access your Unleash instance:

```bash
# Replace <example-unleash> with your Resource Request metadata.name
kubectl port-forward -n example-unleash svc/example-unleash 4242
```

Go to http://localhost:4242. The default credentials are:

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
