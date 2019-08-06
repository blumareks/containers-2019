# containers-2019
The workshop on containers in Silicon Valley. If you like it, please star it!

This page is here:
[ibm.biz/sv-containers-2019](http://ibm.biz/sv-containers-2019)

## Start with the lite account

Sign up for the [IBM Cloud lite account: cloud.ibm.com](https://ibm.biz/Bdzm8w)

## Kubernetes basics - CLI

In order to work with Kubernetes in the command line you need to install the following:
- curl - for downloading tools
- git - for downloading the git repo
- ibm cloud cli - for interacting with ibm cloud
- kubectl - for interacting with kubernetes

On Ubuntu Linux run this command: `sudo apt install curl git` ,
on Mac, since `curl` comes with the system, you can run just this: `brew install git`

**Now you are ready to install IBM Cloud CLI**

On Linux: `curl -fsSL https://clis.ng.bluemix.net/install/linux | sh` ,
on Mac: `curl -fsSL https://clis.ng.bluemix.net/install/osx | sh`

Also you need to install the Container plugins for IBM Cloud:
```shell
ibmcloud plugin install -r "IBM Cloud" container-service
ibmcloud plugin install -r "IBM Cloud" container-registry
```

**Finally install Kubectl**

On Linux:

```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
sudo mv kubectl /usr/local/bin
sudo chmod +x /usr/local/bin/kubectl
```

And on Mac:

```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
sudo mv kubectl /usr/local/bin
sudo chmod +x /usr/local/bin/kubectl
```

## Steps to access the Kubernetes cluster

1. `ibmcloud login` you might want to use some parameters when login
2. Set an environment variable for your cluster name: `export MYCLUSTER=<your_cluster_name>`
3. Download the configuration file and certificates for your cluster using the cluster-config command.

```
ibmcloud ks cluster-config $MYCLUSTER
```

4. and then export the resulting env (the example from my setup below)
```
export KUBECONFIG=/Users/your-user/.bluemix/plugins/container-service/clusters/name-of-your-cluster/kube-config-some-details-name-of-your-cluster.yml
```

Checking the access to your cluster: `kubectl get nodes`

## first steps

Get basic information about your cluster and its worker nodes. This information can help you manage your cluster and troubleshoot issues.

1. View details of your cluster. `ibmcloud ks cluster-get $MYCLUSTER`
2. Verify the worker nodes in the cluster. `ibmcloud ks workers $MYCLUSTER`
and check one of the worker nodes: `ibmcloud ks worker-get <worker_ID>`

3. Validate access to your cluster.
a. View nodes in the cluster. `kubectl get node`

b. View services, deployments, and pods.

`kubectl get svc,deploy,po --all-namespaces`

## the kube-101 lab
Now you are ready to access Kubernetes 101 workshop - see the link here: https://ibm.gitlab.io/workshop/kube101/


# Creating the Kubernetes cluster
https://cloud.ibm.com/docs/tutorials/multi-region-k8s-cis.html#resilient-and-secure-multi-region-kubernetes-clusters-with-cloud-internet-services


## Couple words on the enterprise grade private docker image repo
Some steps to use private registry  - 

- https://console.bluemix.net/docs/services/Registry/registry_setup_cli_namespace.html#registry_setup_cli_namespace
- https://console.bluemix.net/docs/services/Registry/registry_images_.html#registry_images_
- signing images: https://console.bluemix.net/docs/services/Registry/registry_trusted_content.html#registry_trustedcontent
- enforcing trusted images: https://console.bluemix.net/docs/servBd2HGQices/Registry/registry_security_enforce.html#security_enforce
- Vulnerability advisor https://console.bluemix.net/docs/services/va/va_index.html#va_index
- https://console.bluemix.net/docs/services/Registry/registry_trusted_content.html#registry_trustedcontent

## scan images and verify signatures
image trust https://console.bluemix.net/docs/services/Registry/registry_trusted_content.html#registry_trustedcontent

## locking down Kubernetes with proper RBACs 
- https://cloud.ibm.com/docs/tutorials/users-teams-applications.html#assign-roles-within-the-environment
- https://kubernetes.io/docs/reference/access-authn-authz/rbac/

## discussing resilient multi-region Kubernetes cluster
the simple example of deploying multi-region K8s cluster on IBM Cloud: 
- https://console.bluemix.net/docs/tutorials/multi-region-k8s-cis.html?pos=2#resilient-and-secure-multi-region-kubernetes-clusters-with-cloud-internet-services
- https://www.ibm.com/blogs/bluemix/2018/06/multi-region-kubernetes-applications-ibm-cloud-internet-services/

## Knative
Checkout the docs: https://www.knative.dev/docs/
And clone the following example on IBM Cloud: ```git clone https://github.com/IBM-Cloud/knative-node-deploy```
- some docs: https://www.knative.dev/docs/

## IBM Cloud Private guide
- Please find the architecture details on IBM Cloud Private -  https://github.com/ibm-cloud-architecture/refarch-privatecloud/blob/master/README.md
- terraform process to install the ICP: https://github.com/ibm-cloud-architecture/terraform-module-icp-deploy/blob/master/README.md

## previous meetups on containers
in 2019 we had these webinars on containers:
- [2019.02.06 Docker, Kubernetes, Istio and Knative](https://www.crowdcast.io/e/docker-kubernetes-istio)
- [2019.02.06 Best Practices for Kubernetes](https://www.crowdcast.io/e/best-practices-for-2/register)

in 2018 we ran those webinars on containers:
- [2018.11.13 How to write a "Hello World" in Container technology using Docker, Kubernetes and Istio](https://www.crowdcast.io/e/how-to-write-a-hello/register)
- [2018.11.06 Securing Containers with Istio - cohosted with CodeFresh](https://www.crowdcast.io/e/online-meetup-securing/register)
- [2018.10.23 Container Security with NeuVector and IBM Cloud](https://www.crowdcast.io/e/container-security-with/register)
- [2018.07.10 Introduction to Istio](https://www.crowdcast.io/e/introduction-to-istio/register)
- [2018.07.03 Introduction to Kubernetes](https://www.crowdcast.io/e/introduction-to-3/register)
- [2018.06.26 Introduction to Docker](https://www.crowdcast.io/e/introduction-to-docker/register)
- [2018.06.19 Introduction to Containers](https://www.crowdcast.io/e/introduction-to-2/register)

## subscribe for more
If you want to get updates on this repository please star it. Follow me on Twitter [@blumareks](https://twitter.com/blumareks). Thank you for your interest in this repo.
