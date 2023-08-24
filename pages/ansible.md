<!-- omit from toc -->
# Ansible

Ansible is the base code automator and orchestrator.

Ansible is what deploys all of your infrastructure from the base code.

Ansible checks in and verifies that the code is being maintained in its desired state

When we're deploying copies of our network infrastructure for new development teams or app teams or new production environments, we're maintaining that the network behaves the way the code says it behaves.

To properly understand where Ansible fits into the equation, you must have an understanding of [CICD](cicd.md). Imagine the following pipeline:

1. You deploy a network change to source code.
2. Tests are running confirmed.
3. To make sure that the network isn't impacted in a bad way, the code then gets moved to production where Ansible reads the code and sees a new desired state has arrived.
4. Ansible automatically checks the network for compliance with the new desired state and updates the devices as necessary.

That is infrastructure as code and how it's maintained in a CICD pipeline. This is, in essence, NetDevOps!

<!-- omit from toc -->
## Content

- [Installation](#installation)
- [Modules](#modules)
- [Inventory](#inventory)
- [Playbooks](#playbooks)
- [References](#references)

## Installation

Ansible does not run on Windows! You will need to install it on top of a Linux platform, such as Ubuntu.

## Modules

Ansible is built on Python and has a collection of pre-built Python Scripts called Modules.

The network Module is loaded with a myriad of different network platforms, all containing scripts:

---

P O S T - S N I P P E T - O F - L L - H E R E

---

- Pay close attention to [restconf]

## Inventory

The inventory file contains all the devices Ansible manages.\
`/etc/ansible/hosts`

Devices are specified by IP address or hostname and can be categorized into customizable groups, where the group name is surrounded in brackets:

```yaml
[group1]
1.1.1.1
[group2]
2.2.2.2
```

You can have groups that contain subgroups or ‘children’ groups by specifying with a colon:

```yaml
[supergroup:children]
group1
group2
```

## Playbooks

This is where the automation and orchestration happens…

Ansible works by running modules against whatever devices you define. These modules are also called plays and are executed by the ‘playbook.’

The playbook is a YAML file that outlines the instructions that it needs to run. Ex:

```yaml
---
- name: DESCRIPTION OF THE PLAYBOOK TASK
  hosts: GROUP FROM INVENTORY
  tasks:
    - name: TASK DESCRIPTION 1
      <module>: MODULE COMMAND
    - name: TASK DESCRIPTION 2
      <module>: MODULE COMMAND
```

## References

- [Tech Speaker Series for DevOps Automation Ansible and NSO](https://cisco.webex.com/ec3300/eventcenter/recording/recordAction.do?theAction=poprecord&siteurl=cisco&entappname=url3300&internalRecordTicket=4832534b00000004bb02eadd578af628f17db2786899f66048abd5253e0f85f04505bcb4596d48b7&renewticket=0&isurlact=true&format=short&rnd=6331982986&RCID=98a65a8ceabda3334628c3f457c4e173&rID=157613317&needFilter=false&recordID=157613317&apiname=lsr.php&AT=pb&actappname=ec3300&&SP=EC&entactname=/nbrRecordingURL.do&actname=/eventcenter/frame/g.do)\
Webex Password: `jTsnpfA4`
