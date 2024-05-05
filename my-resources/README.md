
# Please do `git reset --hard v6.8`
kernel version v6.8

# Prerequisite
apt-get update -y && \
apt-get upgrade -y && \
apt-get install flex bison pahole kmod jfsutils reiserfsprogs xfsprogs squashfs-tools btrfs-progs pcmciautils quota ppp nfs-common grub2 iptables bc cpio libelf-dev build-essential libncurses-dev bison flex libssl-dev -y

# linux make alias, to make linux to build into `O` path
alias lm='make O=/workspace/objdir/'


# Build
cd /workspace/linux/
make O=/workspace/objdir/ menuconfig -j3
make O=/workspace/objdir/ all -j3

output:
/workspace/objdir/vmlinux