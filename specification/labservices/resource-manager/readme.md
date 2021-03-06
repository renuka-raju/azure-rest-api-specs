# LabServices

> see https://aka.ms/autorest

This is the AutoRest configuration file for LabServices.



---
## Getting Started
To build the SDK for LabServices, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration



### Basic Information
These are the global settings for the LabServices API.

``` yaml
openapi-type: arm
tag: package-2018-10
```


### Tag: package-2018-10

These settings apply only when `--tag=package-2018-10` is specified on the command line.

``` yaml $(tag) == 'package-2018-10'
input-file:
- Microsoft.LabServices/stable/2018-10-15/ML.json
```

---
# Code Generation


## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-net
  - repo: azure-sdk-for-python
  - repo: azure-sdk-for-java
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-js
  - repo: azure-sdk-for-node
  - repo: azure-sdk-for-ruby
    after_scripts:
      - bundle install && rake arm:regen_all_profiles['azure_mgmt_labservices']
  - repo: azure-resource-manager-schemas
    after_scripts:
      - node sdkauto_afterscript.js labservices/resource-manager
```


## C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.Management.LabServices
  output-folder: $(csharp-sdks-folder)/labservices/Microsoft.Azure.Management.LabServices/src/Generated
  clear-output-folder: true
```

## Python

These settings apply only when `--python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.
Use `--python-mode=update` if you already have a setup.py and just want to update the code itself.

``` yaml $(python) && !$(track2)
python-mode: create
python:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  payload-flattening-threshold: 2
  namespace: azure.mgmt.labservices
  package-name: azure-mgmt-labservices
  clear-output-folder: true
```
``` yaml $(python) && $(track2)
python-mode: create
azure-arm: true
license-header: MICROSOFT_MIT_NO_VERSION
namespace: azure.mgmt.labservices
package-name: azure-mgmt-labservices
clear-output-folder: true
```
``` yaml $(python) && $(python-mode) == 'update' && !$(track2)
python:
  no-namespace-folders: true
  output-folder: $(python-sdks-folder)/labservices/azure-mgmt-labservices/azure/mgmt/labservices
```
``` yaml $(python) && $(python-mode) == 'create' && !$(track2)
python:
  basic-setup-py: true
  output-folder: $(python-sdks-folder)/labservices/azure-mgmt-labservices
```
``` yaml $(python) && $(python-mode) == 'update' && $(track2)
no-namespace-folders: true
output-folder: $(python-sdks-folder)/labservices/azure-mgmt-labservices/azure/mgmt/labservices
```
``` yaml $(python) && $(python-mode) == 'create' && $(track2)
basic-setup-py: true
output-folder: $(python-sdks-folder)/labservices/azure-mgmt-labservices
```

## Go

See configuration in [readme.go.md](./readme.go.md)

## Java

These settings apply only when `--java` is specified on the command line.
Please also specify `--azure-libraries-for-java-folder=<path to the root directory of your azure-libraries-for-java clone>`.

``` yaml $(java)
azure-arm: true
fluent: true
namespace: com.microsoft.azure.management.labservices
license-header: MICROSOFT_MIT_NO_CODEGEN
payload-flattening-threshold: 1
output-folder: $(azure-libraries-for-java-folder)/azure-mgmt-labservices
```

### Java multi-api

``` yaml $(java) && $(multiapi)
batch:
  - tag: package-2018-10
```

### Tag: package-2018-10 and java

These settings apply only when `--tag=package-2018-10 --java` is specified on the command line.
Please also specify `--azure-libraries-for-java=<path to the root directory of your azure-sdk-for-java clone>`.

``` yaml $(tag) == 'package-2018-10' && $(java) && $(multiapi)
java:
  namespace: com.microsoft.azure.management.labservices.v2018_10_15
  output-folder: $(azure-libraries-for-java-folder)/sdk/labservices/mgmt-v2018_10_15
regenerate-manager: true
generate-interface: true
```




## AzureResourceSchema

See configuration in [readme.azureresourceschema.md](./readme.azureresourceschema.md)

