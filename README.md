# ansible_jenkins_pipeline
HW3
the task requirments is defined in task.md



the pipline get the following parameters:
    - user_name
    - host_type
    - password
    - ssh key

* instead of pasing the host ip as a paramter , I passed an inventory file (hosts.txt) to ansible plugin , to test the pipline on the workers 
* List of packages are predefined in the the role install/vars/main.py
* Dedicated config files are predefined templates in configuration/templates (used the example template from class)
    
