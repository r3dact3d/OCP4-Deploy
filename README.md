# OCP_Deploy
Repo for deploying OCP to AWS

## Content

- [Purpose](#purpose)
- [Workflow](#workflow)
- [TODO](#todo)

## Purpose
The purpose of this repo is to:
- Provide a CI/CD method to deploy an OCP4 cluster
- Automated way to destroy cluster
- Provide Day 1 GitOps to setup cluster in uniform "fresh" status

## Workflow
- To deploy OCP4.x
  - Ensure PULL_SECRET GitHub Secret is created and up-to-date
  - Ensure GitHub Secrets for AWS creds are created and valid
  - IDP
    - GitHub IDP is used in this deploy, so a GitHub organization should be created
    - Add the clientSecret to GitHub Secrets as CLIENT_SECRET
    - Update the GitHub Organization name and clientID in idp-oauth.yaml file
  - Create PR to merge deploy.md to main after adding name and date to list
- To destroy OCP4.x
  - Validate artifact for the cluster is still available
  - Ensure GitHub Secrets for AWS creds are created and valid
  - Create PR to merge destroy.md to main after adding name and date to list

## TODO
- Add OCP openshift-installer version as variable
- Day 1 Ops
  - GitHub IDP 
  - User RBAC
  - Remove kubeadmin
