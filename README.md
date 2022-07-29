# detective-platform-helm-chart

This Helm chart packages all relevant resource definitions for deploying the detective-platform on Kubernetes. The deployment is individually configurable and can be managed conveniently via the Helm CLI (https://helm.sh/docs).

## How to install the chart

To install the chart and run the detective-platform, go to the `detective-platform` folder, copy the `local-values.yaml.example` file and remove the `.example` suffix. Insert all mandatory local values and reference this file when running `helm install` via the `-f` flag (e.g. `helm install <release-name> ./<path-to-the-chart> -f ./<path-to-the-chart>/local-values.yaml`). After the chart was installed, the platform will be started with the corresponding configuration and will be available on the provided domain.

## Hints for local development

To use the chart for local development, adjust the following properties:

TODO: Simplify configuration to handle most cases via single CLI-call (something like a dev-profile)

1. Set `ingress.domain` to a domain that is locally forwarded to your local cluster's IP address (TODO: Link host forwarding tutorials for MacOS/Windows)
2. Set `ingress.tls.enabled` to `false`
3. Set `enableMonitoringTool` to `true` if needed
4. Set the `auth` secrets as described in `local-values.yaml.example`
5. Check the `appVersion` property in `Chart.yaml` and change if necessary pull a different container version tag

To forward services to a `localhost` port to be accessible by other local services, it is possible to use the Kubernetes CLI or utilize tools like [Kube Forwarder](https://kube-forwarder.pixelpoint.io/) (a predefined configuration file can be found in the `local` folder, which can be imported to Kube Forwarder)
