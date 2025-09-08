# Automation Demo for QeP

Small demo project for demonstration purposes, intended to run in the Ansible Automation Platform deployed in the RedHat Product Demo System.

[![Pre-Commit Hooks](https://github.com/TimGrt/automation-demo/actions/workflows/ci.yml/badge.svg)](https://github.com/TimGrt/automation-demo/actions/workflows/ci.yml) [![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)


The play targets the default `web` group which is present in the already configured inventory.  
To use the demo, create a *Project* with this repository and a Job *Template*. The role defines the default variable `attendee`, define a *Survey* which sets the variable at runtime.  
The playbook will install a webserver on all three nodes with a custom *index.html*.
