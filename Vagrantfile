$bootstrap = <<SCRIPT
sudo apt-get update
sudo apt-get install -y git
git clone https://github.com/som3canadian/Some-Tools.git /home/vagrant/Desktop/Some-Tools/
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "nicmilot/kali-full-2020"
  config.vm.box_version = "1.0.0"
  config.vm.provider "vmware_desktop"
  config.vm.hostname = "kali-full"
  config.vm.provider "vmware_desktop" do |v|
   v.gui = true
   v.linked_clone = false
   v.vmx["memsize"] = "4096"
   v.vmx["numvcpus"] = "2"
  end
  config.vm.provision "shell", privileged: false, inline: $bootstrap
end