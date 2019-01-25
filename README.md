# containers-2019
The workshop on containers in Silicon Valley. If you like it, please star it!

This page is here:
[ibm.biz/sv-containers-2019](ibm.biz/sv-containers-2019)

## Start with the lite account

Sign up for the [IBM Cloud lite account: cloud.ibm.com](https://ibm.biz/Bd2HGQ)

## Creating the Kubernetes cluster
https://cloud.ibm.com/docs/tutorials/multi-region-k8s-cis.html#resilient-and-secure-multi-region-kubernetes-clusters-with-cloud-internet-services


## Couple words on the enterprise grade private docker image repo
Some steps to use private registry  - 

- https://console.bluemix.net/docs/services/Registry/registry_setup_cli_namespace.html#registry_setup_cli_namespace
- https://console.bluemix.net/docs/services/Registry/registry_images_.html#registry_images_
- enforcing trusted images: https://console.bluemix.net/docs/services/Registry/registry_security_enforce.html#security_enforce
- Vulnerability advisor https://console.bluemix.net/docs/services/va/va_index.html#va_index
- https://console.bluemix.net/docs/services/Registry/registry_trusted_content.html#registry_trustedcontent

## scan images and verify signatures
image trust https://console.bluemix.net/docs/services/Registry/registry_trusted_content.html#registry_trustedcontent

## locking down Kubernetes with proper RBACs 
https://cloud.ibm.com/docs/tutorials/users-teams-applications.html#assign-roles-within-the-environment
https://kubernetes.io/docs/reference/access-authn-authz/rbac/
