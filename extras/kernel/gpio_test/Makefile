SHELL := /bin/bash
ifeq (x86_64,$(shell uname -m))
ARCH := arm64
CROSS_COMPILE := aarch64-linux-gnu-
# tries to use "large", and doesn't support "large", "medium", or "kernel"
KBUILD_CFLAGS_MODULE := -mcmodel=small
KDIR := /usr/src/linux-artik
else ifeq (4.4.19-0710GC0F-44F-01QA,$(shell uname -r))
ARCH := arm64
CROSS_COMPILE := aarch64-linux-gnu-
KDIR := /usr/src/linux-artik
else
KDIR := /lib/modules/$(shell uname -r)/build/
endif
obj-m += $(notdir $(PWD)).o
export

all:
	make -C $(KDIR) M=$(PWD) modules
clean:
	make -C $(KDIR) M=$(PWD) clean
env:
	$@
