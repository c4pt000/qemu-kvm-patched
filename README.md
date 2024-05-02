# QEMU README


QEMU is a generic and open source machine & userspace emulator and
virtualizer.

QEMU is capable of emulating a complete machine in software without any
need for hardware virtualization support. By using dynamic translation,
it achieves very good performance. QEMU can also integrate with the Xen
and KVM hypervisors to provide emulated hardware while allowing the
hypervisor to manage the CPU. With hypervisor support, QEMU can achieve
near native performance for CPUs. When QEMU emulates CPUs directly it is
capable of running operating systems made for one machine (e.g. an ARMv7
board) on a different machine (e.g. an x86_64 PC board).

QEMU is also capable of providing userspace API virtualization for Linux
and BSD kernel interfaces. This allows binaries compiled against one
architecture ABI (e.g. the Linux PPC64 ABI) to be run on a host using a
different architecture ABI (e.g. the Linux x86_64 ABI). This does not
involve any hardware emulation, simply CPU and syscall emulation.

QEMU aims to fit into a variety of use cases. It can be invoked directly
by users wishing to have full control over its behaviour and settings.
It also aims to facilitate integration into higher level management
layers, by providing a stable command line interface and monitor API.
It is commonly invoked indirectly via the libvirt library when using
open source applications such as oVirt, OpenStack and virt-manager.

QEMU as a whole is released under the GNU General Public License,
version 2. For full licensing details, consult the LICENSE file.





# Building on Fedora 39

QEMU is multi-platform software intended to be buildable on all modern
Linux platforms, OS-X, Win32 (via the Mingw64 toolchain) and a variety
of other UNIX targets. The simple steps to build QEMU are:


https://docs.fedoraproject.org/en-US/quick-docs/virtualization-getting-started/

```
sudo yum install virt-manager -y
sudo dnf install @virtualization -y
sudo systemctl start libvirtd
sudo systemctl enable libvirtd
sudo virt-manager 
```

```

  sudo -i
  yum install dnf-utils cmake git -y
  yum-builddep qemu -y
  yum groupinstall "C Development Tools and Libraries" -y
  git clone https://github.com/c4pt000/qemu-kvm-patched
  cd qemu-kvm-patched
  mkdir build
  cd build
  ../configure --prefix=/usr
  make -j24
  make -j24 install
```

PfSense WIFI with qemu+KVM
==========================

pfsense 2.7.2 iso release amd64

* https://sgpfiles.netgate.com/mirror/downloads/pfSense-CE-2.7.2-RELEASE-amd64.iso.gz

PfSense 2.7.2 KVM settings

# Freebsd 14.0 machine type (x86_64) with virt-manager

![s1](https://github.com/c4pt000/qemu-kvm-patched/releases/download/pfsense-images/KVM-pfsense-2.7.2.png)


Dlink DWA-556 802.11n best support with pfsense 2.7.2

 ![s1](https://github.com/c4pt000/qemu-kvm-patched/releases/download/pfsense-images/dwa-556.png)




Additional information can also be found online via the QEMU website:

* `<https://wiki.qemu.org/Hosts/Linux>`_
* `<https://wiki.qemu.org/Hosts/Mac>`_
* `<https://wiki.qemu.org/Hosts/W32>`_


