apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: weatherapp
  namespace: argocd
spec:
  project: default

  source:
    repoURL: https://github.com/Zivgl66/k8s-weatherapp
    targetRevision: HEAD
    path: manifest
  destination:
    server: https://kubernetes.default.svc
    namespace: myapp
  syncPolicy:
   automated:
    prune: true
    selfHeal: true