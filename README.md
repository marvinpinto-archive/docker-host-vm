Docker Host VM
--------------

This is a slightly customized version of the default host used by the docker
provider in vagrant.

### Example

Clone this repo somewhere and reference its `Vagrantfile` using the
`vagrant_vagrantfile` parameter in the vagrant file for your docker project.
For example:

```ruby
Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "nginx"
    d.ports = ["80:80", "443:443"]

    # Docker host VM
    d.vagrant_vagrantfile = "/Users/marvin/projects/docker-host-vm/Vagrantfile"
    d.vagrant_machine = "docker-host-vm"
  end
end
```

Using the example above, you should then be able to head over to
`http://192.168.50.4` and get the "Welcome to nginx!" default page.

### More context

- [Default docker host VM][1] (Vagrantfile)
- [Vagrant Docker provider][2]

[1]: https://github.com/mitchellh/vagrant/blob/master/plugins/providers/docker/hostmachine/Vagrantfile
[2]: https://docs.vagrantup.com/v2/docker/index.html
