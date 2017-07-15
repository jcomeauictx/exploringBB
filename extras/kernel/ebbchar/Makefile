ifneq (,$(ARTIK7))
ARCH := arm64
CROSS_COMPILE := aarch64-linux-gnu-
KBUILD_CFLAGS += -mcmodel=kernel
KDIR := /usr/src/linux-artik
else
KDIR := /lib/modules/$(shell uname -r)/build/
endif
obj-m+=ebbchar.o
export

all:
	make -C $(KDIR) M=$(PWD) modules
	$(CC) testebbchar.c -o test
clean:
	make -C $(KDIR) M=$(PWD) clean
	rm test
