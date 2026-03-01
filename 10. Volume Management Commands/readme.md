# Linux Volume Management with AWS EBS and LVM

This guide explains how to manage storage dynamically on a Linux system,
particularly when using Amazon EC2 and EBS volumes with LVM (Logical Volume
Manager). The instructions cover physical volumes, volume groups, logical
volumes, and mounting procedures.

---

## 🎯 Project Goal

Learn to implement Linux volume management using:
- AWS EC2
- AWS EBS volumes
- Linux LVM (Logical Volume Manager)

You will see how to attach, format, combine, and resize storage devices in a
cloud environment.

---

## 1. Introduction to Volumes and EBS

### What is a Volume in Linux?
A volume is simply a storage device (disk or partition) attached to the system.
Common device names include:
```
/dev/xvda
/dev/xvdf
/dev/sdb
```

### What is AWS EBS?
Amazon Elastic Block Store (EBS) provides block-level storage for EC2
instances. Think of it as a virtual hard disk that you can attach to an
instance.

---

## 2. LVM Concepts: PV, VG & LV

The core of LVM revolves around three building blocks:

### 🧱 Physical Volume (PV)
A physical disk or partition prepared for LVM.
```bash
pvcreate /dev/xvdf       # create a PV
pvs                      # list existing PVs
```

### 📦 Volume Group (VG)
A collection of one or more physical volumes that form a storage pool.
```bash
vgcreate tws_vg /dev/xvdf /dev/xvdg
vgs                      # display volume groups
```

### 📂 Logical Volume (LV)
A virtual partition carved out of a volume group. It can be resized
on-the-fly.
```bash
lvcreate -L 10G -n tws_lv tws_vg
```

---

## 3. Mounting Logical Volumes

After creating a logical volume, format and mount it:
```bash
mkfs.ext4 /dev/tws_vg/tws_lv     # format LV
mkdir /data                      # create mount point
mount /dev/tws_vg/tws_lv /data   # mount it

df -h                            # verify
```
To make the mount persistent, add this line to `/etc/fstab`:
```
/dev/tws_vg/tws_lv   /data   ext4   defaults   0 0
```

---

## 4. Managing AWS EBS on an EC2 Instance

### Steps Overview
1. Launch an EC2 instance
2. Attach additional EBS volumes
3. SSH into the instance
4. Check attached disks with `lsblk`

Example output:
```
xvda   20G
xvdf   10G
xvdg   10G
xvdh   10G
```
The extra disks (`xvdf`, `xvdg`, `xvdh`) are used to build an LVM setup.

### Why Use LVM?
LVM offers:
- Dynamic resizing of storage
- Combining multiple disks into a single pool
- Easy expansion and management
- Flexibility beyond traditional partitioning

---

## 5. Using LVM with EBS: Step-by-Step

### Step 1: Create Physical Volumes
```bash
pvcreate /dev/xvdf /dev/xvdg /dev/xvdh
pvs                     # list PVs
pvdisplay               # detailed PV info
```

### Step 2: Create a Volume Group
```bash
vgcreate tws_vg /dev/xvdf /dev/xvdg
vgs                     # view VGs
```

### Step 3: Create a Logical Volume
```bash
lvcreate -L 10G -n tws_lv tws_vg
```

### Step 4: Format and Mount
```bash
mkfs.ext4 /dev/tws_vg/tws_lv
mkdir /data
mount /dev/tws_vg/tws_lv /data

df -h
```

For persistent mounting, add the LV to `/etc/fstab`.


### Mounting the LV (Recap)
- **Path:** `/dev/tws_vg/tws_lv`
- **Mount command:** `mount /dev/tws_vg/tws_lv /data`

Add to `/etc/fstab` for automatic mounting on boot.

---

## 6. Mounting a Disk Without LVM

If you choose not to use LVM, you can mount a raw disk directly:
```bash
mkfs.ext4 /dev/xvdh
mkdir /backup
mount /dev/xvdh /backup
```

---

## 📊 Useful Commands
| Command    | Purpose                     |
|------------|-----------------------------|
| `lsblk`    | List block devices          |
| `df -h`    | Show disk usage             |
| `pvs`      | Show physical volumes       |
| `vgs`      | Show volume groups          |
| `lvs`      | Show logical volumes        |
| `pvdisplay`| Detailed physical volume info |

---

Keep this Markdown as a reference while working with volumes on Linux,
especially in cloud environments with AWS and LVM!