# logipack

Welcome to Cloud Shell! Type "help" to get started.
Your Cloud Platform project in this session is set to logipack-201010.
Use “gcloud config set project [PROJECT_ID]” to change to a different project.
rherrad@cloudshell:~ (logipack-201010)$
rherrad@cloudshell:~ (logipack-201010)$ curl -L https://github.com/jenkins-x/jx/releases/download/v1.3.79/jx-linux-amd64.tar.gz | tar xzv
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   612    0   612    0     0   1463      0 --:--:-- --:--:-- --:--:--  1464
  0 17.4M    0     0    0     0      0      0 --:--:--  0:00:01 --:--:--     0jx
100 17.4M  100 17.4M    0     0  2480k      0  0:00:07  0:00:07 --:--:-- 3877k
rherrad@cloudshell:~ (logipack-201010)$ sudo mv jx /usr/local/bin
rherrad@cloudshell:~ (logipack-201010)$ ll
-bash: ll: command not found
rherrad@cloudshell:~ (logipack-201010)$ export PATH=$PATH:.
rherrad@cloudshell:~ (logipack-201010)$ jx create cluster gke --skip-login
helm not found
? Missing required dependencies, deselect to avoid auto installing: helm
Downloading https://storage.googleapis.com/kubernetes-helm/helm-v2.9.1-linux-amd64.tar.gz to /home/rherrad/.jx/bin/helm.tgz...
Downloaded /home/rherrad/.jx/bin/helm.tgz
error: error installing helm: failed to run '/home/rherrad/.jx/bin/helm plugin install https://github.com/futuresimple/helm-secrets' command in directory '', output: 'Error: plugin home "$HELM_HOME/plugins" does not exist
': exit status 1
rherrad@cloudshell:~ (logipack-201010)$ jx create cluster gke --skip-login
? Google Cloud Project: logipack-201010
Updated property [core/project].
Lets ensure we have container and compute enabled on your project via: gcloud services enable container compute
Waiting for async operation operations/tmo-acf.167e01c3-551d-4ac4-b7d8-3fa33b80628a to complete...
Operation finished successfully. The following command can describe the Operation details:
 gcloud services operations describe operations/tmo-acf.167e01c3-551d-4ac4-b7d8-3fa33b80628a
Waiting for async operation operations/tmo-acf.c33582dc-0294-4582-ac8b-c84b7695d051 to complete...
Operation finished successfully. The following command can describe the Operation details:
 gcloud services operations describe operations/tmo-acf.c33582dc-0294-4582-ac8b-c84b7695d051
No cluster name provided so using a generated one: trackshore
? Google Cloud Zone: europe-west1-c
? Google Cloud Machine Type: n1-standard-1
? Minimum number of Nodes 3
? Maximum number of Nodes 5
Creating cluster...
Initialising cluster ...
? Please enter the name you wish to use with git:  rherrad
? Please enter the email address you wish to use with git:  rherrad@gmail.com
Git configured for user: rherrad and email rherrad@gmail.com
Trying to create ClusterRoleBinding your-active-configuration-is-cloudshell-12788-rherrad-gmail-com-cluster-admin-binding for role: cluster-admin for user Your active configuration is: [cloudshell-12788]
rherrad@gmail.com
Created ClusterRoleBinding your-active-configuration-is-cloudshell-12788-rherrad-gmail-com-cluster-admin-binding
Created ServiceAccount tiller in namespace kube-system
Trying to create ClusterRoleBinding tiller for role: cluster-admin and ServiceAccount: kube-system/tiller
Created ClusterRoleBinding tiller
Initialising helm using ServiceAccount tiller in namespace kube-system
helm installed and configured
? No existing ingress controller found in the kube-system namespace, shall we install one? Yes
Waiting for external loadbalancer to be created and update the nginx-ingress-controller service in kube-system namespace
Note: this loadbalancer will fail to be provisioned if you have insufficient quotas, this can happen easily on a GKE free account. To view quotas run: gcloud compute project-info describe
External loadbalancer created
Waiting to find the external host name of the ingress controller Service in namespace kube-system with name jxing-nginx-ingress-controller
You can now configure a wildcard DNS pointing to the new loadbalancer address 35.233.21.67
? Domain 35.233.21.67.nip.io
nginx ingress controller installed and configured
Lets set up a git username and API token to be able to perform CI/CD

? GitHub user name: rherrad
To be able to create a repository on GitHub we need an API Token
Please click this URL https://github.com/settings/tokens/new?scopes=repo,read:user,read:org,user:email,write:repo_hook,delete_repo

Then COPY the token and enter in into the form below:

? API Token: *****************************************
Cloning the Jenkins X cloud environments repo to /home/rherrad/.jx/cloud-environments
Counting objects: 793, done.
Total 793 (delta 0), reused 0 (delta 0), pack-reused 793
Generated helm values /home/rherrad/.jx/extraValues.yaml
Installing Jenkins X platform helm chart from: /home/rherrad/.jx/cloud-environments/env-gke
waiting for install to be ready, if this is the first time then it will take a while to download images
Jenkins X deployments ready in namespace jx


        ********************************************************

             NOTE: Your admin password is: fighterdog

        ********************************************************

        Getting Jenkins API Token
using url http://jenkins.jx.35.233.21.67.nip.io/me/configure
unable to automatically find API token with chromedp using URL http://jenkins.jx.35.233.21.67.nip.io/me/configure
Please go to http://jenkins.jx.35.233.21.67.nip.io/me/configure and click Show API Token to get your API Token
Then COPY the token and enter in into the form below:

? API Token: ********************************
Created user admin API Token for Jenkins server jenkins.jx.35.233.21.67.nip.io at http://jenkins.jx.35.233.21.67.nip.io
Creating default staging and production environments
Using git provider GitHub at https://github.com


About to create repository environment-trackshore-staging on server https://github.com with user rherrad


Creating repository rherrad/environment-trackshore-staging
Creating git repository rherrad/environment-trackshore-staging
Pushed git repository to https://github.com/rherrad/environment-trackshore-staging

Created environment staging
Created Jenkins Project: http://jenkins.jx.35.233.21.67.nip.io/job/rherrad/job/environment-trackshore-staging/

Note that your first pipeline may take a few minutes to start while the necessary docker images get downloaded!

Creating github webhook for rherrad/environment-trackshore-staging for url http://jenkins.jx.35.233.21.67.nip.io/github-webhook/
Using git provider GitHub at https://github.com


About to create repository environment-trackshore-production on server https://github.com with user rherrad


Creating repository rherrad/environment-trackshore-production
Creating git repository rherrad/environment-trackshore-production
Pushed git repository to https://github.com/rherrad/environment-trackshore-production
rherrad@cloudshell:~ (logipack-201010)$ jx create spring -d web -d actuator
? Language: java
? Group: com.logisur
? Artifact: logipack
Created spring boot project at /home/rherrad/logipack
? Do you wish to use rherrad as the git user name: Yes
The directory /home/rherrad/logipack is not yet using git
? Would you like to initialise git now? Yes
? Commit message:  Initial import

Git repository created
selected pack: /home/rherrad/.jx/draft/packs/github.com/jenkins-x/draft-packs/packs/maven
replacing placeholders in directory /home/rherrad/logipack
app name: logipack, git server: github.com, org: rherrad
Using git provider GitHub at https://github.com


About to create repository logipack on server https://github.com with user rherrad
? Which organisation do you want to use? rherrad
? Enter the new repository name:  logipack
Creating repository rherrad/logipack
Pushed git repository to https://github.com/rherrad/logipack
Created Jenkins Project: http://jenkins.jx.35.233.21.67.nip.io/job/rherrad/job/logipack/
Watch pipeline activity via:    jx get activity -f logipack -w
Browse the pipeline log via:    jx get build logs rherrad/logipack/master
Open the Jenkins console via    jx console
You can list the pipelines via: jx get pipelines
When the pipeline is complete:  jx get applications
For more help on available commands see: https://jenkins-x.io/developing/browsing/
Note that your first pipeline may take a few minutes to start while the necessary docker images get downloaded!
Creating github webhook for rherrad/logipack for url http://jenkins.jx.35.233.21.67.nip.io/github-webhook/
rherrad@cloudshell:~ (logipack-201010)$ jx get activity -f logipack -w
STEP                         STARTED AGO DURATION STATUS
rherrad/logipack/master #1         1m46s          Running
  Checkout Source                   1m2s      12s Succeeded
  CI Build and push snapshot         49s          NotExecuted
  Build Release                      48s          Pending
^C
rherrad@cloudshell:~ (logipack-201010)$ jx console
Jenkins Console: http://jenkins.jx.35.233.21.67.nip.io/blue
