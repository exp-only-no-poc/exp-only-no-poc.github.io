---
title: Project offer: Smashing VMware for fun and profit
tags: vmware hypervisor project_offer
---

### Project Introduction

VMware is a hypervisor product to virtualizing an OS as a process.

VMware workstation( for Windows ) and VMware Fusion( for MacOS ) is a Type 2 hypervisor which it emulates necessary hardware components like storage( NVME, SCSI...), graphics( SVGA... ), network( e1000e, vmxnet... ) implementation within the process with corresponding MMIO or I/O port handlers.

VMware ESXi is a Type 1 hypervisor like qemu-kvm or hyper-v. It 'communicates' with kernel-land in host machine with hypercall instruction. It also emulates some hardware components like type 2 hypervisors but it contains less implementation because of its nature.


The goal of this project is finding and exploiting vulnerabilities in VMware workstation/VMware Fusion products.

Maybe someone asks "why not VirtualBox? it is open-source, pwn2own target with decent prize...". But I think it is **too easy** target for collaboration project.
If you are targeting VMware workstation on Windows, you will face closed-source binary with 50000-80000 functions( based on IDA ) with [CFG](https://learn.microsoft.com/en-us/windows/win32/secbp/control-flow-guard) enabled.

It will be fun! and quite hard if you don't have any experience on auditing hypervisor products before...But it is solvable problem with collaboration( at least I believe so ).

There are some public references which you can understand some basic vulnerability patterns in VMware:
- https://www.reversetactics.com/publications/2020_conf_ekoparty_speedpwning_vmware/
- https://awxylitol.github.io/2023/09/08/rogue-cdb-escaping-from-vmware-workstation-through-the-disk-controller.html
- https://theori.io/blog/chaining-n-days-to-compromise-all-part-5-vmware-workstation-host-to-guest-escape
- https://i.blackhat.com/EU-24/Presentations/EU24-Lee-Guest-Revolution.pdf
- https://powerofcommunity.net/assets/v0/poc2024/Nguyen%20Hoang%20Thach,%20VMware%20Workstation%20-%20Escaping%20via%20a%20New%20Route%20-%20Virtual%20Bluetooth.pdf

You can tried to use LLM( maybe with ida-pro-mcp? ) to understand( or untangling ) the closed-source codes like [Qrious Secure did](https://github.com/qriousec/vmware_re). I am not the one who thinks AI will take our jobs but I believe it will accelerates our capability more than ever 😎.

Send DM to [@exp_only_no_poc](https://x.com/exp_only_no_poc) on X platform if you have any interest for this project!

---
