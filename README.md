# QHub
Automated data science platform. From [JupyterHub](https://jupyter.org/hub "Multi-user version of the Notebook") to
Cloud environments with [Dask Gateway](https://docs.dask.org/ "Parallel computing in Python").

[![PyPI version](https://badge.fury.io/py/qhub.svg)](https://badge.fury.io/py/qhub)

QHub is an open source tool that enables users to build and maintain
cost-effective and scalable compute/data science platforms on [HPC](#qhub-hpc) or on [Kubernetes](#qhub) with minimal DevOps
experience.

**This repository details the [QHub](https://qhub.dev/ "Official QHub docs") (Kubernetes) version.**

Not sure what to choose? Check out our [Setup Initialization](docs/source/02_get_started/02_setup.md) page.

## QHub HPC

Version of QHub based on OpenHPC.

> NOTE: The tool is currently under development. Curious? Check out the [Qhub HPC](https://github.com/Quansight/qhub-hpc) repository.

## QHub

The Kubernetes version of QHub is built using [Terraform](https://www.terraform.io/), [Helm](https://helm.sh/), and
[GitHub Actions](https://docs.github.com/en/free-pro-team@latest/actions).
Terraform handles the build, change, and versioning of the infrastructure. Helm helps to define, install, and manage
[Kubernetes](https://kubernetes.io/ "Automated container deployment, scaling, and management"). GitHub
Actions is used to automatically create commits when the configuration file (`qhub-config.yaml`) is rendered, as well as
to kick off the deployment action.

QHub aims to abstract all these complexities for its users. Hence, it is not necessary to know any of the above mentioned
technologies to have your project successfully deployed.

> TLDR:
> If you know GitHub and feel comfortable generating and using API keys, you should have all it takes to deploy
> and maintain your system without the need for a dedicated DevOps team. No need to learn Kubernetes, Terraform, or Helm.

### Cloud Providers
QHub offers out-of-the-box support for [Digital Ocean](https://www.digitalocean.com/), Amazon [AWS](https://aws.amazon.com/), [GCP](https://cloud.google.com/ "Google Cloud Provider"), and Microsoft [Azure](https://azure.microsoft.com/en-us/).

![High-level illustration of QHub architecture](docs/source/images/qhub-cloud_architecture.png)

For more details, check out the release [blog post](https://www.quansight.com/post/announcing-qhub).

## Installation
### Pre-requisites
* QHub is supported by macOS and Linux operating systems (Windows is **NOT** currently supported).
* Compatible with Python 3.6+. New to Python? We recommend using [Anaconda](https://www.anaconda.com/products/individual).
* Adoption of virtual environments (`conda`, `pipenv` or `venv`) is also encouraged.

### Install
To install QHub run:
* `conda`:
  ```bash
  conda install -c conda-forge qhub
  ```

* or `pip`:
    ```bash
    pip install qhub
    ```
Once finished, you can check QHub's version (and additional CLI args) by typing:
```
qhub --help
```
If successful, the CLI output will be similar to the following:

```bash
usage: qhub [-h] [-v] {deploy,destroy,render,init,validate} ...

QHub command line

positional arguments:
  {deploy,destroy,render,init,validate}
                        QHub

optional arguments:
  -h, --help            show this help message and exit
  -v, --version         QHub version
```

## Usage
QHub requires the setting of environment variables to automate the deployments fully. For details on how to obtain those
variables, check the [Step-by-Step](https://docs.qhub.dev/en/latest/source/03_tutorials_and_samples/1_project_setup_tutorial.html) guide in the docs.

Once all the necessary credentials are gathered and set as [UNIX environment variables](https://linuxize.com/post/how-to-set-and-list-environment-variables-in-linux/),
QHub can be deployed in under 20 minutes using:
```bash
qhub init   ... # generates initial config file and optionally automates deployment steps
qhub deploy ... # creates and configures the cloud infrastructure
```

## Questions?
Have a look at our [FAQ](docs/source/02_get_started/07_support.md#faq) to see if your query has been answered.

We separate the queries for QHub into:
* [GitHub Discussions](https://github.com/Quansight/qhub/discussions) used to raise discussions about a subject, such as:
"What is the recommended way to do X with QHub?"
* [Issues](https://github.com/Quansight/qhub/issues/new/choose) for queries, bug reporting, feature requests,
  documentation, etc.
> We work around the clock to make QHub more excellent, but sometimes your query might take a while to get a reply. We apologise in advance and ask you to please, be patient.


## Code of Conduct
To guarantee a welcoming and friendly community, we require contributors to follow our
[Code of Conduct](https://github.com/Quansight/.github/blob/master/CODE_OF_CONDUCT.md).


## Developer
To install the latest developer version (unstable) use:
```bash
pip install git+https://github.com/Quansight/qhub.git@dev
```

## Contributions
Thinking about contributing? Check out our [Contribution Guidelines](https://github.com/Quansight/qhub/blob/main/CONTRIBUTING.md).

## License
[QHub is BSD3 licensed](LICENSE).
