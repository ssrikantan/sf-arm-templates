# Azure Service Fabric ARM Templates

ARM Templates 3NodetypeELBSFCluster.json and 3NodetypeILBSFCluster.json perform similar deployments. The only difference between them is that the former uses an External Load Balancer with the Public IP Address, whereas the latter uses an Internal load balancer. Some of the usage scenarios are:

* Deploy a new Service Fabric Cluster into an existing VNet + Subnet and in the same Azure region as the latter
* Enable IMDS (Instance Metadata Services Endpoint) on the VM Scale set used in the Cluster
* It is assumed that a Key Vault exists, and a certificate is available in it that can be used in the SF Cluster
* It assumes that the Admin Client certificate is created on the User Store of the Computer that would act as an Admin Client that connects to the Service Fabric cluster
* A 3 -Node Type cluster is created by this Template

## ARM Template - 1NodetypeELBSFClusterLatest.json
- enables the ResourceMonitorService in the Cluster
- adds version 6.2.194.1 manually into the configuration
- updated API version for the Service Fabric cluster - 2018-02-01
