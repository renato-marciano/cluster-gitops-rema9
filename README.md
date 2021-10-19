# Introduction

This repository is a GitOps repo with manifests observed by Flux and representing what is deployed on K8s clusters.

The intent of this Repo is to host auto-generated manifests by a Github Action triggered in [Multicloud Control Plane Repo](https://github.com/microsoft/multicloud-control-plane-seed). Do not directly commit and push changes to this Repo.

In order for this repository to function as expected in the broader solution, we assume that you have templated the [Multicloud Control Plane Seed Repo](https://github.com/microsoft/multicloud-control-plane-seed) and have configured the GitHub Action Workflow

## Getting Started

### Deploy your Cluster(s)

Deploy your cluster(s) using your preferred method to the cloud provider(s) of your choosing

### Create your Cluster GitOps Repo

[Use this template](https://github.com/microsoft/multicloud-control-plane-cluster-gitops/generate) to create a new repository.

### Generate `/applications` and `clusters` Directories

Running the GitHub Action in the Control Plane Repo once application and clusters are registered will kick off a transformation that will generate the directories in this repository as defined in the Control Plane.

### Install Flux & deploy your manifests

Install [Flux v2](https://fluxcd.io/docs/cmd/flux_bootstrap/) onto your cluster(s) and point to correct directories in this repository. The manifests should deploy once boostrapped.

## "Dialtone Services" Provided

NOTE for MSFT Devs: this will likely change as we rearchitect how we think about dialtone services as apps.

The `./infrastructure` directory includes the definitions for services provided out-of-the-box to deploy to and harness in a cluster:

* [Prometheus](https://prometheus.io/)
* [Grafana](https://grafana.com/)
* [Contour](https://projectcontour.io/)

These are referenced for deployment to clusters as part of the GitHub Actions write into this repository.

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit <https://cla.opensource.microsoft.com>.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft
trademarks or logos is subject to and must follow
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.

## References

1. [Flux](https://fluxcd.io/docs/get-started/)
1. [GitOps](https://www.weave.works/technologies/gitops/)
