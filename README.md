# Distribution Registry stack for Kubernetes on Wodby

Deploy a private CNCF Distribution Registry v3 on Wodby.

The stack contains:

- a required Distribution Registry service with a 20 GiB persistent volume;
- an optional, enabled-by-default Valkey metadata cache configured as a
  disposable `allkeys-lru` cache.

Basic authentication is enabled by default. Attach an AWS, GCP, or generic
S3-compatible storage integration for object storage, or keep the default
persistent filesystem backend. Delegated token authentication can be connected
by adding a compatible `distribution-auth` service to a derived stack.

<!-- wodby:generated:start -->

## Stack contract

- [Distribution Registry stack on Wodby](https://wodby.com/stacks/distribution)
- [Browse Wodby application stacks](https://wodby.com/stacks)
- [Wodby stack documentation](https://wodby.com/docs/2.0/stacks/)
- [Stack manifest reference](https://wodby.com/docs/2.0/stacks/template/)

## Service definitions

- [Distribution Registry service](https://github.com/wodby/service-distribution)
- [Valkey service](https://github.com/wodby/service-valkey)

## What's included

| Component / service | Default configuration |
| --- | --- |
| Distribution Registry<br>`registry` | required; enabled by default; volumes: `data` 20 GB; links: `redis` → `registry-cache` |
| Registry metadata cache<br>`registry-cache` | optional; enabled by default |

Enabled optional services are selected by default but can be excluded when an
app is created. Disabled optional services are available but not selected by
default. Required services cannot be excluded.

## Validate the stack manifest

```bash
wodby stack validate-manifest stack.yml --org <org-id>
```

<!-- wodby:generated:end -->
