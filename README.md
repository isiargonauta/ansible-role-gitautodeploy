Role Name
=========

Machines with this role will have a small HTTP server that listens for Web hook requests sent from GitHub, GitLab or Bitbucket servers. 
That application allows you to continuously and automatically deploy you projects each time you push new commits to your repository.
See this [link](http://olipo186.github.io/Git-Auto-Deploy/)

Requirements
------------

ansible >= 1.7.2
Tested against Debian Etch 6.0.8

Role Variables
--------------

gitautodeploy_install_scope: user #dont change this. Only user scope implemented, makes local user install.
gitautodeploy_service_port: 8001 #The port for the web server to listen on.
gitautodeploy_repo1_name: Git-Auto-Deploy #Repo to clone locally and track pushes for
gitautodeploy_push_trigger_repo1_base_url: https://github.com/olipo186 #Base url for the repo.
gitautodeploy_push_trigger_repo1_branch: master #Branch to be tracked
gitautodeploy_pull_trigger_repo1_base_url: https://api.github.com/repos/olipo186 #Repo to clone locally and track PR for
gitautodeploy_pull_trigger_repo1_branch: testing-branch #Branch to be tracked

Dependencies
------------

None

Example Playbook
----------------


    - hosts: servers
      roles:
         - { role: argonauta.gitautodeploy, gitautodeploy_service_port: 8003 }

License
-------

BSD

Author Information
------------------

rich at argonauta dot org
