# Lab 1 Terraform

This is my Lab 1 in Terraform.

In this lab, I made a project where I used Terraform to describe a Linux VM in Google Cloud. I also added a backup policy and a GitHub Actions pipeline to check the code.

## What I did

I created Terraform code for:

- an Ubuntu VM in GCP
- a startup script with simple hardening
- a snapshot policy for backup
- a GitHub Actions workflow for lint, security scan, validate, and plan

## Files in the project

- main.tf - the main resources
- variables.tf - variables
- outputs.tf - outputs from Terraform
- startup.sh - script that runs when the VM starts
- .github/workflows/terraform.yml - pipeline in GitHub Actions
- .gitignore - makes sure sensitive and local files do not end up in Git

## Security

In startup.sh I added:

- ufw
- fail2ban
- unattended-upgrades

I chose this so the VM gets a simple basic security setup from the start.

## Commands I used

To start Terraform:
terraform init

To check that the code is valid:
terraform validate

To see what Terraform wants to create:
terraform plan

To try to create the resources:
terraform apply

## Pipeline

I made a GitHub Actions pipeline that runs:

- terraform fmt -check -recursive
- Trivy scan
- terraform validate
- terraform plan

## Result

The Terraform code passed validate and plan.

I also created a pull request in GitHub and got green checks for:

- lint
- security
- validate
- plan

## Problems I ran into

When I ran terraform apply locally, it did not work because my account did not have enough permissions in GCP to create the VM and backup policy.

To continue, I added GCP_SA_KEY to GitHub Actions secrets. After that, terraform plan worked in CI.

## Screenshots

For the final submission, I will include:

- a screenshot of the pull request with green checks
- a screenshot of the VM in GCP Console if the deployment is completed later
