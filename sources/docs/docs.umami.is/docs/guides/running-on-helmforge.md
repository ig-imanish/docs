# Source: https://docs.umami.is/docs/guides/running-on-helmforge

Menu

Hosting

# Running on Kubernetes with HelmForge

Copy page

[HelmForge](https://helmforge.dev/docs/charts/umami/) provides a third-party Helm chart for running Umami on Kubernetes. The chart uses the official Umami container image and can deploy PostgreSQL as a bundled subchart or connect to an external PostgreSQL database.

## Requirements[#](https://docs.umami.is/docs/guides/running-on-helmforge#requirements)

- A working Kubernetes cluster.
- Helm 3 installed locally.
- A default `StorageClass` if you use the bundled PostgreSQL subchart.
- Optional: an Ingress controller if you want to expose Umami with a public hostname.

## Add the HelmForge repository[#](https://docs.umami.is/docs/guides/running-on-helmforge#add-the-helmforge-repository)

```shell
helm repo add helmforge https://repo.helmforge.dev
helm repo update
```

## Install with bundled PostgreSQL[#](https://docs.umami.is/docs/guides/running-on-helmforge#install-with-bundled-postgresql)

For a basic installation, the chart can deploy Umami together with PostgreSQL:

```shell
kubectl create namespace umami

helm install umami helmforge/umami \
  --namespace umami
```

Access the application locally with port forwarding:

```shell
kubectl port-forward \
  --namespace umami \
  svc/umami-umami 3000:80
```

Then open `http://localhost:3000`. The default login credentials are username **admin** and password **umami**.

Change the default password

Change the default password immediately after your first login.

## Use an external PostgreSQL database[#](https://docs.umami.is/docs/guides/running-on-helmforge#use-an-external-postgresql-database)

To connect Umami to an existing PostgreSQL database, disable the bundled PostgreSQL subchart and provide the external database settings:

```yaml
# values.yaml
postgresql:
  enabled: false

database:
  external:
    host: postgres.example.com
    port: "5432"
    name: umami
    username: umami
    existingSecret: umami-db-credentials
    existingSecretPasswordKey: password
```

Then install the chart with:

```shell
helm install umami helmforge/umami \
  --namespace umami \
  --values values.yaml
```

## Expose with Ingress[#](https://docs.umami.is/docs/guides/running-on-helmforge#expose-with-ingress)

For a public installation, enable Ingress:

```yaml
ingress:
  enabled: true
  ingressClassName: nginx
  hosts:
    - host: analytics.example.com
      paths:
        - path: /
          pathType: Prefix
  tls:
    - hosts:
        - analytics.example.com
      secretName: umami-tls
```

## More information[#](https://docs.umami.is/docs/guides/running-on-helmforge#more-information)

- [HelmForge Umami chart documentation](https://helmforge.dev/docs/charts/umami/)
- [HelmForge Umami chart source](https://github.com/helmforgedev/charts/tree/main/charts/umami)

[PreviousRunning on Koyeb](https://docs.umami.is/docs/guides/running-on-koyeb) [NextRunning on Neon Postgres](https://docs.umami.is/docs/guides/running-on-neon)

On this page