# IBM Cloud Pak System Software on Power VS

[![Graduated (Supported)](https://img.shields.io/badge/status-Graduated%20(Supported)-brightgreen?style=plastic)](https://terraform-ibm-modules.github.io/documentation/#/badge-status)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
[![latest release](https://img.shields.io/github/v/release/terraform-ibm-modules/terraform-ibm-powervs-sap?logo=GitHub&sort=semver)](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/releases/latest)
[![Renovate enabled](https://img.shields.io/badge/renovate-enabled-brightgreen.svg)](https://renovatebot.com/)

## Summary
This repository contains deployable architecture solutions that help in deploying Power Virtual Server for IBM Cloud Pak System. The solutions are available in the IBM Cloud Catalog and can also be deployed without the catalog, except for a few solutions.


### IBM catalog solutions that require a Schematics workspace ID of [Power Virtual Server with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global)
1. [IBM catalog PowerVS SAP Ready variation](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/tree/main/solutions/ibm-catalog/sap-ready-to-go)
    - Creates and configures **one HANA instance, zero to several NetWeaver instances, and one optional ShareFS** with **RHEL or SLES OS** distribution. Creates a private subnet for SAP communication for the entire landscape.
    - Optionally configures OS network management services (NTP, NFS, and DNS services) using Ansible Galaxy Collection from [IBM](https://galaxy.ansible.com/ui/repo/published/ibm/power_linux_sap/): `power_linux_sap`
    - Additionally tunes the instances according to SAP's best practices, which are fully ready for hosting SAP applications.




## Reference architectures
- [IBM Cloud Pak System Software for POWER](https://github.com/terraform-ibm-modules/terraform-ibm-cps/blob/gayathri-1/images/IBM_Cloud_Pak_System_Software_for_POWER/deploy-arch-ibm-CPS-pvs-inf-standard.svg)


## Solutions
|                                  Variation                                  | Available on IBM Catalog | Requires Schematics Workspace ID | Creates PowerVS with VPC landing zone | Creates PowerVS HANA Instance | Creates PowerVS NW Instances | Performs PowerVS OS Config | Performs PowerVS SAP Tuning | Install SAP software |
|:---------------------------------------------------------------------------:|:------------------------:|:--------------------------------:|:-------------------------------------:|:-----------------------------:|:----------------------------:|:--------------------------:|:---------------------------:|:--------------------:|
| [ IBM catalog PowerVS SAP Ready ]( ./solutions/ibm-catalog/sap-ready-to-go/ ) |    :heavy_check_mark:    |        :heavy_check_mark:        |                  N/A                  |               1               |            0 to N            |     :heavy_check_mark:     |      :heavy_check_mark:     |          N/A         |
| [ IBM catalog SAP S/4HANA or BW/4HANA variation ]( ./solutions/ibm-catalog/sap-s4hana-bw4hana ) |    :heavy_check_mark:    |        :heavy_check_mark:        |                  N/A                  |               1               |            1            |     :heavy_check_mark:     |      :heavy_check_mark:     |          :heavy_check_mark:         |
|             [ PowerVS SAP Ready ]( ./solutions/sap-ready-to-go/ )             |            N/A           |                N/A               |                  N/A                  |               1               |            0 to N            |     :heavy_check_mark:     |      :heavy_check_mark:     |          N/A         |
|                      [ End-to-End ]( ./solutions/e2e/ )                     |            N/A           |                N/A               |           :heavy_check_mark:          |               1               |            0 to N            |     :heavy_check_mark:     |      :heavy_check_mark:     |          N/A         |



## Required IAM access policies

You need the following permissions to run this module.

- Account Management
    - **Resource Group** service
        - `Viewer` platform access
    - IAM Services
        - **Workspace for Power Systems Virtual Server** service
        - **Power Systems Virtual Server** service
            - `Editor` platform access
        - **VPC Infrastructure Services** service
            - `Editor` platform access
        - **Transit Gateway** service
            - `Editor` platform access
        - **Direct Link** service
            - `Editor` platform access

## Contributing

You can report issues and request features for this module in GitHub issues in the module repository. See [Report an issue or request a feature](https://github.com/terraform-ibm-modules/.github/blob/main/.github/SUPPORT.md).

To set up your local development environment, see [Local development setup](https://terraform-ibm-modules.github.io/documentation/#/local-dev-setup) in the project documentation.
<!-- END CONTRIBUTING HOOK -->