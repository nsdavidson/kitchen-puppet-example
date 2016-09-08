## Puppet/InSpec

### Install the things
Either add `kitchen-puppet` to your Gemfile and run a `bundle install` or install the gem directly with a `gem install kitchen-puppet`.

You will also need copies of Facter, Hiera and Puppet installed (https://downloads.puppetlabs.com/mac/)

### Kitchen config
Set your provisioner to be `puppet_apply` and set `manifests_path` to point to the manifests you want to test.
```
provisioner:
  name: puppet_apply
  manifests_path: manifests
```

You can specify multiple suites, you'll just need to create a test manifest file to apply the things you want to run for that suite.
```suites:
  - name: default
    provisioner:
      manifest: test_lamp.pp
  - name: user
    provisioner:
      manifest: test_user.pp```

More info:
kitchen-puppet -> https://github.com/neillturner/kitchen-puppet/
InSpec example -> https://github.com/chef/inspec/tree/master/examples/kitchen-puppet
