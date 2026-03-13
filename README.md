# Lab 1 Terraform

This project creates a Linux VM in Google Cloud using Terraform. It also includes a startup script for basic hardening, a daily backup policy, and a GitHub Actions pipeline for validation and security checks.

## How to run

terraform init

terraform plan

terraform apply

## Security decisions

I used ufw, fail2ban, and unattended-upgrades in the startup script.

I chose ufw to limit incoming traffic, fail2ban to help protect against repeated login attempts, and unattended-upgrades to help keep the system updated with security patches.

## Screenshots

Pipeline screenshot:

![Pipeline checks](images/pipeline-checks.png)

VM screenshot from GCP Console:

![GCP VM](images/gcp-vm.png)
