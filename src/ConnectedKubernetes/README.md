<!-- region Generated -->
# Az.ConnectedKubernetes
This directory contains the PowerShell module for the ConnectedKubernetes service.

---
## Status
[![Az.ConnectedKubernetes](https://img.shields.io/powershellgallery/v/Az.ConnectedKubernetes.svg?style=flat-square&label=Az.ConnectedKubernetes "Az.ConnectedKubernetes")](https://www.powershellgallery.com/packages/Az.ConnectedKubernetes/)

## Info
- Modifiable: yes
- Generated: all
- Committed: yes
- Packaged: yes

---
## Detail
This module was primarily generated via [AutoRest](https://github.com/Azure/autorest) using the [PowerShell](https://github.com/Azure/autorest.powershell) extension.

## Module Requirements
- [Az.Accounts module](https://www.powershellgallery.com/packages/Az.Accounts/), version 2.7.5 or greater

## Authentication
AutoRest does not generate authentication code for the module. Authentication is handled via Az.Accounts by altering the HTTP payload before it is sent.

## Development
For information on how to develop for `Az.ConnectedKubernetes`, see [how-to.md](how-to.md).
<!-- endregion -->

---
## Generation Requirements
Use of the beta version of `autorest.powershell` generator requires the following:
- [NodeJS LTS](https://nodejs.org) (10.15.x LTS preferred)
  - **Note**: It *will not work* with Node < 10.x. Using 11.x builds may cause issues as they may introduce instability or breaking changes.
> If you want an easy way to install and update Node, [NVS - Node Version Switcher](../nodejs/installing-via-nvs.md) or [NVM - Node Version Manager](../nodejs/installing-via-nvm.md) is recommended.
- [AutoRest](https://aka.ms/autorest) v3 beta <br>`npm install -g autorest@beta`<br>&nbsp;
- PowerShell 6.0 or greater
  - If you don't have it installed, you can use the cross-platform npm package <br>`npm install -g pwsh`<br>&nbsp;
- .NET Core SDK 2.0 or greater
  - If you don't have it installed, you can use the cross-platform npm package <br>`npm install -g dotnet-sdk-2.2`<br>&nbsp;

## Run Generation
In this directory, run AutoRest:
> `autorest`

---
### AutoRest Configuration
> see https://aka.ms/autorest

``` yaml
branch: 9a19506631005d0ff1e3f394c86a9ce10cf51910
require:
  - $(this-folder)/../readme.azure.noprofile.md
input-file:
  - $(repo)/specification/hybridkubernetes/resource-manager/Microsoft.Kubernetes/stable/2021-10-01/connectedClusters.json

title: ConnectedKubernetes
module-version: 0.1.0
subject-prefix: $(service-name)

identity-correction-for-post: true
resourcegroup-append: true
nested-object-to-string: true

directive:
  - where:
      subject: ^ConnectedCluster(.*)
    set:
      subject: $1
  - where:
      variant: ^Create$|^CreateViaIdentity$|^CreateViaIdentityExpanded$|^Update$|^UpdateViaIdentity$
      subject-prefix: ConnectedKubernetes
    remove: true
  - where:
      subject-prefix: ConnectedKubernetes
      parameter-name: ClusterName
    set:
      alias: Name
  - where:
      verb: Update
      subject-prefix: ConnectedKubernetes
      parameter-name: Property
    hide: true
  - where:
      verb: New|Update|Remove
      subject-prefix: ConnectedKubernetes
    hide: true

```
