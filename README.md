# WSL2-KVM-MacOs
```
sudo apt install -y libvirt-daemon-system-sysv
sudo apt-get install qemu-system qemu-utils python3 python3-pip
sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils

sudo service libvirtd start
sudo service virtlogd start

sudo usermod -G  kvm "username"
sudo chmod 666 /dev/kvm

git clone https://github.com/foxlet/macOS-Simple-KVM
cd macOS-Simple-KVM
./jumpstart.sh --mojave

qemu-img create -f qcow2 MyDisk.qcow2 64G

and add it to the end of basic.sh:
    -drive id=SystemDisk,if=none,file=MyDisk.qcow2 \
    -device ide-hd,bus=sata.4,drive=SystemDisk \

./make.sh --add
virt-manager



```
