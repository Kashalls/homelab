---
template: main.html
---

# Codename: Nezuko

This custom built machine is named after a very popular character of the [`Demon Slayer: Kimetsu no Yaiba`](https://www.imdb.com/title/tt9335498/) series. During the entire series of the show, Nezuko slowly turns into a demon, however maintains her elegance throughout. This is the inspiration I came up with to build this pc.

## Machine Specs

- [AMD Ryzen 9 3900X](https://www.amazon.com/AMD-Ryzen-3900X-24-Thread-Processor/dp/B07SXMZLP9)
- [AsRock Rack X470D4U](https://www.asrockrack.com/general/productdetail.asp?Model=X470D4U#Specifications)
- [MSI Ventus GeForce RTX 2060](https://www.newegg.com/msi-geforce-rtx-2060-g2060vgp12c/p/N82E16814137719?quicklink=true)
- [Corsair RM650x](https://www.newegg.com/corsair-rmx-series-rm650x-2018-cp-9020178-na-650w/p/N82E16817139232?Item=N82E16817139232)
- [LIAN LI LANCOOL II MESH](https://www.newegg.com/white-lian-li-lancool-ii-rgb-mesh-atx-mid-tower/p/2AM-000Z-00087?Item=9SIAFSTFNJ2221)

## Operating System

As of writing this, Nezuko is running [`Proxmox 7.1-12`](https://www.proxmox.com/en/news/press-releases/proxmox-virtual-environment-7-1-released) and is running **2** Ubuntu VM's acting as a k8s master and worker as well as a [freepbx](https://www.freepbx.org/) vm for my home phone system (although I will be migrating to Unifi Talk soon...)

### Storage

I've populated both of the onboard NVME slots with [Crucial P1 1TB M.2 NVMe](https://www.crucial.com/ssd/eol_p1/ct1000p1ssd8) SSD's. This motherboard however does not allocate the full bandwidth to utilize these drives.
