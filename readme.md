[comment]: # "Auto-generated SOAR connector documentation"
# Nutanix Prism

Publisher: Nutanix  
Connector Version: 1\.0\.0  
Product Vendor: Nutanix  
Product Name: Prism  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.0\.1068  

This app implements the virtualization actions for Nutanix Prism

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Prism asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**username** |  required  | string | Admin Username
**password** |  required  | password | Admin Password
**base\_url** |  required  | string | IP or Hostname of CVM

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[get system info](#action-get-system-info) - Get information about a VM  
[list vms](#action-list-vms) - Get the list of registered VMs  
[revert vm](#action-revert-vm) - Revert VM to specified snapshot  
[snapshot vm](#action-snapshot-vm) - Take a snapshot of the VM  
[start vm](#action-start-vm) - Start a stopped or suspended VM  
[stop vm](#action-stop-vm) - Stop a VM  
[suspend vm](#action-suspend-vm) - Suspend a VM \(Requires guest tools installed on vm\)  
[search vms](#action-search-vms) - Query VM's based on string  
[list snapshots](#action-list-snapshots) - List snapshots in a cluster  
[get snapshot info](#action-get-snapshot-info) - Get information of a specific snapshot  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'get system info'
Get information about a VM

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vm\_uuid** |  required  | UUID of VM to get info of | string |  `vm path`  `uuid` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.vm\_uuid | string |  `vm path`  `uuid` 
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'list vms'
Get the list of registered VMs

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'revert vm'
Revert VM to specified snapshot

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vm\_uuid** |  required  | UUID of VM to restore | string |  `vm path`  `uuid` 
**snapshot\_uuid** |  optional  | UUID of Snapshot | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.vm\_uuid | string |  `vm path`  `uuid` 
action\_result\.parameter\.snapshot\_uuid | string | 
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'snapshot vm'
Take a snapshot of the VM

Type: **investigate**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vm\_uuid** |  required  | UUID of VM to snapshot | string |  `vm path`  `uuid` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.vm\_uuid | string |  `vm path`  `uuid` 
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'start vm'
Start a stopped or suspended VM

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vm\_uuid** |  required  | UUID of VM to start | string |  `vm path`  `uuid` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.vm\_uuid | string |  `vm path`  `uuid` 
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'stop vm'
Stop a VM

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vm\_uuid** |  required  | UUID of VM to stop | string |  `vm path`  `uuid` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.vm\_uuid | string |  `vm path`  `uuid` 
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'suspend vm'
Suspend a VM \(Requires guest tools installed on vm\)

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vm\_uuid** |  required  | UUID of VM to suspend | string |  `vm path`  `uuid` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.vm\_uuid | string |  `vm path`  `uuid` 
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'search vms'
Query VM's based on string

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**search\_string** |  required  | Query VM's based on string | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.search\_string | string | 
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'list snapshots'
List snapshots in a cluster

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get snapshot info'
Get information of a specific snapshot

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**snapshot\_uuid** |  required  | UUID of Snapshot | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.snapshot\_uuid | string | 
action\_result\.status | string | 
action\_result\.data | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 