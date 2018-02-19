# CiscoLive 2018 Breakout Examples

### Create Access Port Profile Playbook
```create_accportprof_playbook.yml``` - Create access port profile playbook. This playbook should be called including credentials variables (Similar to those located in ```aci_creds.yml```) and a list of infrastructure variables (Similar to ```aci_accportprof_vars.yml```).

The following roles are used in this playbook:
* ```aci_create_snapshot``` - Create a configuration snapshot on APIC prior to making changes.
* Create a new interface policy leaf profile on APIC and add a number of interface selectors and interface blocks.
* Add the newly created leaf profile in the previous role to an existing switch policy leaf profile.

### Delete Access Port Profile Playbook
```delete_accportprof_playbook.yml``` - Delete access port profile playbook. This playbook should be called including credentials variables (Similar to those located in ```aci_creds.yml```) and a list of infrastructure variables (Similar to ```aci_accportprof_vars.yml```).

The following roles are used in this playbook:
* ```aci_create_snapshot```
* ```aci_delete_switch_profile_Leaf_101_and_102```
* ```aci_delete_leafprofile```
