# detective-platform-helm-chart

This Helm chart packages all relevant resource definitions for deploying the detective-platform on Kubernetes. The deployment is individually configurable and can be managed conveniently via the Helm CLI (https://helm.sh/docs).

## How to install the chart

The install the chart and run the detective-platform, go to the `detective-platform` folder, copy the `local-values.yaml.example` file and remove the `.example` suffix. Insert all mandatory local values and reference this file when running `helm install` via the `-f` flag (e.g. `helm install <release-name> ./<path-to-the-chart> -f ./<path-to-the-chart>/local-values.yaml`). The chart will be installed and the platform will be started with the corresponding configuration after a successful installation.
