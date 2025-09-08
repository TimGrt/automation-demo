# Automation Demo for QeP

Small demo project for demonstration purposes, intended to run in the Ansible Automation Platform deployed in the RedHat Product Demo System.

[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/TimGrt/automation-demo/main.svg)](https://results.pre-commit.ci/latest/github/TimGrt/automation-demo/main)

The play targets the default `web` group which is present in the already configured inventory.  
To use the demo, create a *Project* with this repository and a Job *Template*. The role defines the default variable `attendee`, define a *Survey* which sets the variable at runtime.  
The playbook will install a webserver on all three nodes with a custom *index.html*.
