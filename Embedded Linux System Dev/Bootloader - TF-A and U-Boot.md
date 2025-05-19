# Bootloader – TF-A and U-Boot
*Objectives: Set up serial communication, compile and install the U-Boot bootloader, use basic U-Boot commands, set up TFTP communication with the development workstation.*

## Issue
The instructions say you need to run `make` with the given `DEVICE_TREE`:

```bash
make DEVICE_TREE=stm32mp157a-dk1
```

You can find your Device Tree file in the [Bootlin Buildroot External ST Repository](https://github.com/bootlin/buildroot-external-st).

Just follow the instructions in the `README.md`. The setup can be completed very quickly.

---

## ⚠️ Build Failure: Fakeroot Header Issue

The build may fail again.

The reason: the header of **fakeroot** is not defined correctly — specifically, the line:

```c
#define _STAT_VER 1
```

is missing.

To fix this issue, you need to use an updated version of the Fakeroot package.

👉 Use this [Buildroot patch](https://git.busybox.net/buildroot/commit/?id=f45925a951318e9e53bead80b363e004301adc6f) and replace the **Fakeroot package** in your Buildroot with the patched one.

---

There are some other approaches, such as manually defining `_STAT_VER`, but many users report that these do not work reliably.

So for a proper fix, it's best to update the Fakeroot package as described above.

For Korean speakers, this [blog post](http://blog.naver.com/chandong83/223060211213) provides a detailed explanation (I think). 
It’s the source where I first found the solution.


