# Install Application Single Sign-On

The AppSSO package is currently published as part of the Tanzu Application Platform package repository.

---

👉 If you are already running TAP with `run`, `iterate`, or `full` profiles, AppSSO is installed already. However, you
may want to review its configuration.

---

## What's inside

The AppSSO package will install the following resources:

* The `appsso` Namespace with a Deployment of the AppSSO controller and Services for Webhooks
* A `ServiceAccount` with RBAC outlined in detail [here](./rbac.md)
* [`AuthServer` and `ClientRegistration` CRDs](../crds/index.md)

## Prerequisites

Before installing AppSSO, please ensure you have Tanzu Application Platform installed on your Kubernetes cluster.

## Installation

1. Learn more about the AppSSO package:

   ```shell
   tanzu package available get sso.apps.tanzu.vmware.com --namespace tap-install
   ```

1. Install the AppSSO package:

   ```shell
   tanzu package install appsso \
     --namespace tap-install \
     --package-name sso.apps.tanzu.vmware.com \
     --version {{ vars.app-sso.version }}
   ```

1. Confirm the package has reconciled successfully:

   ```shell
   tanzu package installed get appsso --namespace tap-install
   ```
