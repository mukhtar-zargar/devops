# Steps for creating helm chart

- helm create chart-name
- important files/folder:
  - Chart.yaml: Chart description
    - dependencies: other chart dependencies
  - values.yaml: variables to use throughout
    - use dependency chart name as key to pass values to them
  - templates: custom k8 yaml configs
- helm dependency build/update [install/update dependencies]
- helm template --debug [path (.)] -- doesn't send file to kube server
  OR
- helm install --dry-run --debug [path (.)] -- does send file to kube server
- helm install [chart-name] [chart-path]
- helm status/get/uninstall [chart-name]
- helm package --sign ./mychart --key mykey --keyring ~/.gnupg/secring.gpg
