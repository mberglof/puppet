Puppet
======

## Tool-box

Script and git-hook to synchronise manifests from a GIT
repository to the Puppet master:
https://github.com/pdxcat/puppet-sync

A gitflow fork which works with github and pull-requests.
Info: http://datasift.github.io/gitflow/index.html
Code: https://github.com/datasift/gitflow

Things to look at:
http://rspec-puppet.com/
https://puppetlabs.com/automation-2/video-continuous-integration-for-your-puppet-code/

Testing
-------
(puppetlabs_spec_helper)[https://github.com/puppetlabs/puppetlabs_spec_helper]

Environments
------------

The gitflow model have two main branches, master (renamed to
production to avoid name collission in puppet.conf) and develop,
which we'll map to puppet environments on the puppet master.


### feature (always branches off develop)
The 'develop' branch is where stuff get made.
Should really be deployed to VM's running on your local machine.

### develop
The 'develop' branch is where stuff get made.
Should really be deployed to VM's running on your local machine.

### release
When all the major features has been merged into develop and doesn't
break shit it's time to make a release branch which can be deployed to UAT.
Fix bugs -> merge to develop -> test -> repeat
Tag the release and pull-request to production.

### production
Review and merge pull request.
If possible the merge should trigger puppet-sync which will deploy the branch.

Git
---

### Subtree

