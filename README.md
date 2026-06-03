# workloads — app-of-apps master (Forgejo)

ArgoCD (in the admin cluster) watches this repo through the single GitHub→Forgejo
bridge Application (`gitops/admin/apps/workloads-root.yaml` in the platform repo).
Every `*.yaml` here is an ArgoCD `Application`/`ApplicationSet` for a workload.

Adding a workload = a Forgejo-only change: commit a new manifest here plus its
`<app>` (code) and `<app>-config` (manifests) repos. The platform (GitHub) keeps
just the one bridge.

| File           | Workload                                               |
|----------------|--------------------------------------------------------|
| `demo-app.yaml`| demo-app → test + prod, sourced from `demo-app-config` |
