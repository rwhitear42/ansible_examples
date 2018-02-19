# CiscoLive 2018 Breakout Examples

### Create Access Port Profile Playbook
```create_accportprof_playbook.yml``` - Create access port profile playbook. This playbook should be called including credentials variables (Similar to those located in ```aci_creds.yml```) and a list of infrastructure variables (Similar to ```aci_accportprof_vars.yml```).

The following roles are used in this playbook:
* ```aci_create_snapshot``` - Create a configuration snapshot on APIC prior to making changes.
* ```aci_create_leafprofile``` - Create a new interface policy leaf profile on APIC and add a number of interface selectors and interface blocks.
* ```aci_create_switch_profile_Leaf_101_and_102``` - Add the newly created leaf profile in the previous role to an existing switch policy leaf profile.

**_Example:_** ```ansible-playbook -e @aci_creds.yml -e @aci_accportprof_vars.yml create_accportprof_playbook.yml```

```
PLAY [Access Port Profile Playbook] *******************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************
ok: [apic.cisco.com]

TASK [aci_create_snapshot : Create a Snapshot] ********************************************************************************************
changed: [apic.cisco.com]

TASK [aci_create_leafprofile : Create Access Port Leaf Profile] ***************************************************************************
changed: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 31, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_1'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 32, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_2'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 33, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_3'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 34, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_4'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 35, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_5'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 36, u'interface_policy_group': u'1Gbps_acc_to_win_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'windows_servers', u'description_of_attached_device': u'windows_svr_1'})

TASK [aci_create_switch_profile_Leaf_101_and_102 : Create Access Port Leaf Profile] *******************************************************
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 31, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_1'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 32, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_2'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 33, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_3'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 34, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_4'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 35, u'interface_policy_group': u'1Gbps_acc_to_esx_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'esx_hosts', u'description_of_attached_device': u'esx_host_5'})
ok: [apic.cisco.com] => (item={u'leaf_profile_name': u'Leaf_101_and_102', u'description': u'Leaf_101_and_102', u'interface_number': 36, u'interface_policy_group': u'1Gbps_acc_to_win_host', u'status_is': u'created,modified', u'description_of_attached_devices': u'windows_servers', u'description_of_attached_device': u'windows_svr_1'})

PLAY RECAP ********************************************************************************************************************************
apic.cisco.com              : ok=4    changed=2    unreachable=0    failed=0


```


### Delete Access Port Profile Playbook
```delete_accportprof_playbook.yml``` - Delete access port profile playbook. This playbook should be called including credentials variables (Similar to those located in ```aci_creds.yml```) and a list of infrastructure variables (Similar to ```aci_accportprof_vars.yml```).

The following roles are used in this playbook:
* ```aci_create_snapshot```
* ```aci_delete_switch_profile_Leaf_101_and_102```
* ```aci_delete_leafprofile```
