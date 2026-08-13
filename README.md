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

Validate the manifest with:

```bash
wodby stack validate-manifest stack.yml --org <org-id>
```
