$script = <<SCRIPT
  pacman -Syyu --needed --noconfirm
  pacman -S --needed --noconfirm \
    base-devel \
    asciidoc \
    avr-gcc \
    avr-binutils \
    avr-libc \
    bc \
    cdrkit \
    dfu-util \
    fastjar \
    gtk2 \
    intltool \
    unzip \
    arm-none-eabi-gcc \
    arm-none-eabi-binutils \
    arm-none-eabi-newlib \
    git \
    diffutils
SCRIPT

Vagrant.configure(2) do |config|
 
   config.vm.box = "terrywang/archlinux"
 
   config.vm.provider "virtualbox" do |v|
     v.memory = 2048
     v.cpus = 2
   end

   config.vm.provision "shell", inline: $script

   config.vm.post_up_message = <<-EOT
     Log into the VM using 'vagrant ssh' on OSX or from Git Bash (Win)
     or 'vagrant ssh-config' and Putty or Bitvise SSH or another SSH tool
   EOT
 
end