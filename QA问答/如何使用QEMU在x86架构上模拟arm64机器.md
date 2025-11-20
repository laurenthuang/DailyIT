## 如何使用 qemu 在 x86 架构上模拟 arm64 机器

1. 先下载从 debian 官网下载 nocloud 镜像：debian-13-nocloud-arm64.qcow2
2. 执行如下命令（方括号中参数可选）

```shell
$ sudo qemu-system-arm64 \
  -machine virt \
  -m 4096 -cpu max \
  -drive file=debian-13-nocloud-arm64.qcow2,media=disk,if=virtio \
  -netdev passt,id=n1[,dns=<ip of dns>] -device virtio-net-pci,netdev=n1 \
  -virtfs local,path=<to be shared in the host>,security_model=passthrough,id=host_share -bios /usr/share/qemu-efi-aarch64/QEMU_EFI.fd
```

💡 `-cpu max` 兼容最多的 ARM 指令集
