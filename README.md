__GitOps__
================================

GitOps implementation with  GitlabCI, ArgoCD and HELM

![Screenshot](GitOpsImage.png)

Basic settings
------------
* GitLab CI Pipeline
* Kubernetes template using Helm Charts
* Continuous Deployment using ArgoCD
* GitOps repository structure

Gitlab repository structure
------------
![Screenshot](Topology.png)

Note
------------
You can add variables in Gitlab at the group level from Settings -> CICD -> Variables

* CD_ARGOCD_URL: argocd.local.az
* CD_ARGOCD_USERNAME: argo
* CD_ARGOCD_PASSWORD: password
* CI_GITLAB_REGISTRY_URL: gitlab.local.az:4567
* CI_GITLAB_REGISTRY_USERNAME: admin_registry
* CI_GITLAB_REGISTRY_PASSWORD: password
* CI_GITLAB_USERNAME: admin_ci
* CI_GITLAB_PASSWORD: password
* CI_PROJECT_TEMPLATE: cicd/demo/ci-template
* CD_GITLAB_PROJECT: cicd
* EXPO_USERNAME: expo
* EXPO_PASSWORD: passowrd

----

* The following stages are for the backend, frontend and mobile. 

stages:
  - package
  - image_build
  - push_to_helm
  - argocd_sync
  - deploy_to_expo

* The package stage is undergoing the build operation.
* The image_build stage creates an image from Dockerfile.
* The push_to_helm stage writes a new image tag id to the helm repo.
* The argocd_sync stage synchronizes the application in argpcd due to a change in the helm repo.
* The deploy_to_expo stage for mobile includes build operations for both android and ios.


__Requirements__
------------
* Gitlab
* ArgoCD
* Helm
* Expo

__Author Information__
------------------

Samir Nabadov
