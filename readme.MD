# Deploy PA Lab

This git repo will be responsible for documentation, deploying, and configuring a PA lab in Azure.

End state will be automatically using Terraform/Ansible/etc. to deploy a PA in Azure, configure interfaces, deploy an app_server VM, and create a tunnel back to Strata Cloud Manager.

Phase one is focused on creating a living document that walk throughs the manual process. This will help us understand the automation workflow, required variables, and how we can interpolate variables together to increase re-use.


### Documentation for Manually Deploying and Configuring:
* Deploy PA in Azure: [Deploy PA in Azure](document_fw_build/0_azure_deploy/azure_build.md)
* Configure Azure: [Configure Azure](document_fw_build/1_azure_configure/azure_configure.md)
* General PA config: [General PA config](document_fw_build/2_base_configure_pa/configure_pa.md)
* General Network Config for PA: [General Network PA Config](document_fw_build/3_general_network_config_pa/3_general_network_config_pa.md)
* General Policy Config for PA: [General Policy PA Config](document_fw_build/4_base_policy_pa/4_base_policy_pa.md)