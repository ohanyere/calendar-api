# Runbook

## Service

- Name: `calendar-api`
- Team: `Commerce`
- Owner: `mooref068@gmail.com`
- Cost center: `commerce`

## First Checks

```bash
kubectl get rollout calendar-api -n calendar-api-dev
kubectl get pods -l app.kubernetes.io/name=calendar-api -n calendar-api-dev
kubectl logs -l app.kubernetes.io/name=calendar-api -n calendar-api-dev
```

## Health

```bash
curl https://calendar-api.dev.platform.ohanyere.internal/healthz
curl https://calendar-api.dev.platform.ohanyere.internal/readyz
curl https://calendar-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo calendar-api -n calendar-api-dev
```

Escalate to `Commerce` through `mooref068@gmail.com` if rollback does not restore service.
