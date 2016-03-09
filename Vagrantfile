# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "oim1admin" , primary: true do |oim1admin|

    oim1admin.vm.box = "OEL6_6-x86_64"
    oim1admin.vm.box_url = "https://dl.dropboxusercontent.com/s/i247jykp2obw3ln/OEL6_6-x86_64.box"

    oim1admin.vm.provider :vmware_fusion do |v, override|
      override.vm.box = "OEL-6.6-x86_64-vmware"
      override.vm.box_url = "https://dl.dropboxusercontent.com/s/96qaaklh1ya6qnd/OEL6_6-x86_64-vmware.box"
    end

    oim1admin.vm.hostname = "oim1admin.example.com"

    oim1admin.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]
    # oim1admin.vm.synced_folder "/Users/edwin/software", "/software", :mount_options => ["dmode=777","fmode=777"]


    oim1admin.vm.network :private_network, ip: "10.10.10.61"

    oim1admin.vm.provider :vmware_fusion do |vb|
      vb.vmx["numvcpus"] = "2"
      vb.vmx["memsize"] = "5548"
    end

    oim1admin.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "5548"]
      vb.customize ["modifyvm", :id, "--name"  , "oim1admin"]
      vb.customize ["modifyvm", :id, "--cpus"  , 2]
    end

    oim1admin.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppet/hiera.yaml;rm -rf /etc/puppet/modules;ln -sf /vagrant/puppet/modules /etc/puppet/modules"

    oim1admin.vm.provision :puppet do |puppet|
      puppet.manifests_path    = "puppet/manifests"
      puppet.module_path       = "puppet/modules"
      puppet.manifest_file     = "site.pp"
      puppet.options           = "--verbose --hiera_config /vagrant/puppet/hiera.yaml"

      puppet.facter = {
        "environment"    => "development",
        "vm_type"        => "vagrant",
      }

    end

  end

  config.vm.define "oimnode1" , primary: true do |oimnode1|

    oimnode1.vm.box = "OEL6_6-x86_64"
    oimnode1.vm.box_url = "https://dl.dropboxusercontent.com/s/i247jykp2obw3ln/OEL6_6-x86_64.box"

    oimnode1.vm.provider :vmware_fusion do |v, override|
      override.vm.box = "OEL-6.6-x86_64-vmware"
      override.vm.box_url = "https://dl.dropboxusercontent.com/s/96qaaklh1ya6qnd/OEL6_6-x86_64-vmware.box"
    end

    oimnode1.vm.hostname = "oimnode1.example.com"

    oimnode1.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]
    # oimnode1.vm.synced_folder "/Users/edwin/software", "/software", :mount_options => ["dmode=777","fmode=777"]


    oimnode1.vm.network :private_network, ip: "10.10.10.62"

    oimnode1.vm.provider :vmware_fusion do |vb|
      vb.vmx["numvcpus"] = "2"
      vb.vmx["memsize"] = "3548"
    end

    oimnode1.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "3548"]
      vb.customize ["modifyvm", :id, "--name"  , "oimnode1"]
      vb.customize ["modifyvm", :id, "--cpus"  , 2]
    end

    oimnode1.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppet/hiera.yaml;rm -rf /etc/puppet/modules;ln -sf /vagrant/puppet/modules /etc/puppet/modules"

    oimnode1.vm.provision :puppet do |puppet|
      puppet.manifests_path    = "puppet/manifests"
      puppet.module_path       = "puppet/modules"
      puppet.manifest_file     = "node.pp"
      puppet.options           = "--verbose --hiera_config /vagrant/puppet/hiera.yaml"

      puppet.facter = {
        "environment"    => "development",
        "vm_type"        => "vagrant",
      }

    end

  end

  config.vm.define "oimnode2" , primary: true do |oimnode2|

    oimnode2.vm.box = "OEL6_6-x86_64"
    oimnode2.vm.box_url = "https://dl.dropboxusercontent.com/s/i247jykp2obw3ln/OEL6_6-x86_64.box"

    oimnode2.vm.provider :vmware_fusion do |v, override|
      override.vm.box = "OEL-6.6-x86_64-vmware"
      override.vm.box_url = "https://dl.dropboxusercontent.com/s/96qaaklh1ya6qnd/OEL6_6-x86_64-vmware.box"
    end

    oimnode2.vm.hostname = "oimnode2.example.com"

    oimnode2.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]
    # oimnode2.vm.synced_folder "/Users/edwin/software", "/software", :mount_options => ["dmode=777","fmode=777"]


    oimnode2.vm.network :private_network, ip: "10.10.10.63"

    oimnode2.vm.provider :vmware_fusion do |vb|
      vb.vmx["numvcpus"] = "2"
      vb.vmx["memsize"] = "3548"
    end

    oimnode2.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "3548"]
      vb.customize ["modifyvm", :id, "--name"  , "oimnode2"]
      vb.customize ["modifyvm", :id, "--cpus"  , 2]
    end

    oimnode2.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppet/hiera.yaml;rm -rf /etc/puppet/modules;ln -sf /vagrant/puppet/modules /etc/puppet/modules"

    oimnode2.vm.provision :puppet do |puppet|
      puppet.manifests_path    = "puppet/manifests"
      puppet.module_path       = "puppet/modules"
      puppet.manifest_file     = "node.pp"
      puppet.options           = "--verbose --hiera_config /vagrant/puppet/hiera.yaml"

      puppet.facter = {
        "environment"    => "development",
        "vm_type"        => "vagrant",
      }

    end

  end

  config.vm.define "oimdb" , primary: true do |oimdb|

    oimdb.vm.box = "OEL6_6-x86_64"
    oimdb.vm.box_url = "https://dl.dropboxusercontent.com/s/i247jykp2obw3ln/OEL6_6-x86_64.box"

    oimdb.vm.provider :vmware_fusion do |v, override|
      override.vm.box = "OEL-6.6-x86_64-vmware"
      override.vm.box_url = "https://dl.dropboxusercontent.com/s/96qaaklh1ya6qnd/OEL6_6-x86_64-vmware.box"
    end

    oimdb.vm.hostname = "oimdb.example.com"
    oimdb.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]
    # oimdb.vm.synced_folder "/Users/edwin/software", "/software", :mount_options => ["dmode=777","fmode=777"]

    oimdb.vm.network :private_network, ip: "10.10.10.9"

    oimdb.vm.provider :vmware_fusion do |vb|
      vb.vmx["numvcpus"] = "2"
      vb.vmx["memsize"] = "2532"
    end

    oimdb.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm"     , :id, "--memory", "2532"]
      vb.customize ["modifyvm"     , :id, "--name"  , "oimdb"]
      vb.customize ["modifyvm"     , :id, "--cpus"  , 2]
    end


    oimdb.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppet/hiera.yaml;rm -rf /etc/puppet/modules;ln -sf /vagrant/puppet/modules /etc/puppet/modules"

    oimdb.vm.provision :puppet do |puppet|
      puppet.manifests_path    = "puppet/manifests"
      puppet.module_path       = "puppet/modules"
      puppet.manifest_file     = "db.pp"
      puppet.options           = "--verbose --hiera_config /vagrant/puppet/hiera.yaml"

      puppet.facter = {
        "environment" => "development",
        "vm_type"     => "vagrant",
      }

    end

  end

end
