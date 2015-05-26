radamanth.maven-ansible 
=========

This role install node via nvm.
It will add a nvm user and group to you system.
Then it will nvm, node, and yeoman (because it's great you should use it to start a project) 
You can customize the npm librabry you want installed.
Same goes for the yeoman generator.



Requirements
------------

Ubuntu platform
Ansible 1.9 (use of become) 
The user in users_profiles should exists, they wont be created by this playbook

Role Variables
--------------

```yaml
---
# Nvm user that will own the nvm installation
nvm_user: {user: 'nvm', group: 'nvm', passphrase: "nvmpassphrase" }

#cnvm git repository 
nvm_git_repo: "https://github.com/creationix/nvm.git"
# Nvm version
nvm_version: v0.25.3
# nvm install dir
nvm_install_dir: /opt/nvm
# wich verison of version of node do you desire 
nvm_node_version: '0.12.4'
# any package you would like to ionstall globally ? 
nvm_npm_pkg:
  - bower
  - coffee-script
  - jade
  - less
  - express
  - prettyjson
  - forever
  - grunt-forever
  - pngquant-bin
  - imagemin-gifsicle
  - imagemin-jpegtran
  - imagemin-optipng
  - imagemin-pngquant
  - grunt-cli
# Any Yeoman generator you want at your services?
nvm_yo_gen:
  - generator-angular-fullstack
  - generator-jhipster
# Users profiles that will be updated to have node and nvm in path .
nvm_users_profiles: 
  - { user: "auserwhousenode", group: "hisgroup"}
# Arbitrary phrase playbook  will be looking for in 'nvm ls' result stdout 
nvm_node_default_version_pattern: "node -> stable (-> v{{ nvm_node_version }}) (default)"




```

Dependencies
------------

None


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: maven_servers
      roles:
         - { role: radamanth.node-nvm-ansible, version: 1.0.0 }

License
-------

GPLV2

Author Information
------------------


I've been a computer science engineer for more than 10 years now, I've discovered Ansible in 2014, and fell in love with it. I use it in my company to manage different server since then. Feel free to visit our site www.neovia.fr

I'm also one of the founder of Immozeo, where Ansible is also greatly used. ( www.immozeo.com)

