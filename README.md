# homelab

GitOps manifests for a single-node k3s cluster, reconciled by Argo CD.

- `app-of-apps.yaml` is the Argo CD root. It watches `apps/`.
- `apps/` has one Argo CD Application per workload.
- Platform: cert-manager, sealed-secrets, Argo CD Image Updater, Loki, Tempo, Alloy, Prometheus stack, Headlamp.
- Apps: openGym, portfolio, psst-course, doohickey.

Secrets are Bitnami SealedSecrets. They decrypt only with the cluster's controller key,
which is never stored here. Networking, VPN and DNS live in a separate private repository.
