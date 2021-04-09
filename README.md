## Generic test role using vagrant

### Requirement on the host

- vagrant
- ansible

The role is installed in the `current directory/roles` (see ansible.cfg for details)

### Steps

This is generic test role framework using vagrant

to use to test a role using the default var of the role, just run `ansible-playbook start-test.yaml` in this directory

to run some custom action before applying the role - write a task file named `pre-tasks-for-test-role-<YOUR_ROLE_NAME>.yaml` - it will be executed

to run after the role is called write a task file named `post-tasks-for-test-role-<YOUR_ROLE_NAME>.yaml`

You will be prompt for roles to test

if your role depends on others you can supply in a vars file. Copy the file `test-role-role_name-vars.yaml` to
yours replace the `role_name` with your role name. Edit the file add roles to the vars `test_roles`.

Make sure that you install the ansible galaxy dependencies specified in your role requirements.txt and/or the global requirements.yaml file before proceeding.

If you already have a hosts that you can access then run the playbook `test-host-manual.yaml` instead. Vagrant
is not required for this case
