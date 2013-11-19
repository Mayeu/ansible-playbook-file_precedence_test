#File precedence illustration

Example playbook to illustrate the file precedence.

##Test

Just type:

    $ cat roles/precedence_test/files/test_file
    this file should not be in the VM
    $ cat files/test_file
    this file should be in the VM
    $ vagrant up && vagrant ssh
    # in the VM:
    $ cat /etc/test_file
    this file should be in the VM

The file `files/test_file` had taken precedence over
`roles/precedence_test/files/test_file`
