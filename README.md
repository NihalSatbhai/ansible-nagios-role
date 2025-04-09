
# Ansible Role Name - nagios

## Description

This script automates the process of installing and configuring the nagios package on multiple servers.

## Table of Contents

- [Supported_Target_Environment]
- [Scope_of_the_Script]
- [Hardware_Prerequisites]
- [Server_Requirements]
- [Usage]
- [Role_Variables]
- [Dependencies]
- [Example_Playbook]
- [License]
- [Author_Information]

## Supported Target Environment

The script supports Linux and Debian systems.

## Scope of the Script

The script performs the following tasks:

- Installs the nagios package.
- Configures system settings based on defined users.
- Performs additional tasks specific to the nagios package.

## Hardware Prerequisites

- 2 GB RAM
- 20 GB average local disk storage
- 2 CPU

## Server Requirements

- Ensure sudo access to the server for executing privileged commands.
- Internet access to download the necessary binaries.
- Open firewall rules to allow access to the necessary ports on the server.

## Usage

The main playbook (playbook.yml) should include the package role as shown in the example below:

        ```yaml
        hosts: server
        become: true
        roles:
        - nagios
        ```

The playbook will call the tasks/main.yml file and execute the tasks accordingly.

## Role Variables

The following variables are used in this role:

Variables defined in defaults/main.yml:
- None

Variables defined in vars/main.yml, Which pass through the UI

        ```yaml
        # Specify the version of the package to install
        required_nagios_version: x.x.x
        nagios_plugins_version: x.x.x

        # Specify the username and password to access the default nagios page
        nagios_username: username
        nagios_password: password

        # Specify whether to uninstall the present version of nagios or not
        uninstall_current_version: true/false
        ```

## Dependencies

This role has no dependencies on other roles hosted on Galaxy.

## Example Playbook

An example of how to call the package role with variables passed as parameters:

        ```yaml
        - hosts: testserver
        become: true
        roles:
            - role: nagios
        ```

## License

BSD

## Author Information

Nihal Satbhai