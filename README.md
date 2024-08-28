# ansible_jenkins_pipeline
HW3
the task requirments is defined in task.md



the pipline get the following parameters:
    - user_name
    - host_type
    - password
    - ssh key

* instead of pasing the host ip as a paramter , I passed an inventory file (hosts.txt) to ansible plugin ,easier to test the pipline on the workers  
* List of packages are predefined in the the role install/vars/main.py
* Dedicated config files are predefined templates in conf/templates (used the example template from class)
    
roles:
user_settings role : creates the user with th epassword and the ssh key
install: loops over the vars file and installs the list of packages
conf: copies the jinja templates with the predefined vars to the rempte host