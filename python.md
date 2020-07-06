```
ubuntu@os-helm:~$ cd venv1
ubuntu@os-helm:~/venv1$ source env/bin/activate
(env) ubuntu@os-helm:~/venv1$
(env) ubuntu@os-helm:~/venv1$ ls
env  openrc  openstack_checks.py  os_details.py
(env) ubuntu@os-helm:~/venv1$
(env) ubuntu@os-helm:~/venv1$ python openstack_checks.py
Please enter username (OS_USERNAME) : admin
Please enter password (OS_PASSWORD) :
====================================================================================================
				POST-Deployment Checks of Openstac-Helm
====================================================================================================
----------------------------------------------------------------------------------------------------
	 Glance (test-image) creation check
----------------------------------------------------------------------------------------------------
Status of image(test-image) 		 : active
Image creation				 : Success
Deleting the test-image...
----------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------
	 Network (test-network) creation check
----------------------------------------------------------------------------------------------------
Status of network(test-network)		 : ACTIVE
Network creation			 : Success
Deleting the test-network...
----------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------
	 Volume (test-volume) creation check
----------------------------------------------------------------------------------------------------
Status of volume(test-volume) 		 :  available
Volume creation				 :  Success
Deleting the test-volume...
----------------------------------------------------------------------------------------------------
	 Instance (test-server) creation check
----------------------------------------------------------------------------------------------------
Status of instance(test-server)		 :  ACTIVE
Instance creation			 :  Success
Deleting the test-server...
(env) ubuntu@os-helm:~/venv1$
(env) ubuntu@os-helm:~/venv1$
(env) ubuntu@os-helm:~/venv1$
(env) ubuntu@os-helm:~/venv1$ cat os_details.py
#!/usr/bin/env python3
import getpass
username=input("Please enter username (OS_USERNAME) : ")
password=getpass.getpass("Please enter password (OS_PASSWORD) : ")
project_name='admin'
project_id='91322d21da6945c7b9b202d01db76488'
user_domain_name='default'
user_domain_id='default'
auth_url='http://keystone.openstack.svc.cluster.local/v3'
VERSION = '2'
project_domain_id='default'
(env) ubuntu@os-helm:~/venv1$


```
