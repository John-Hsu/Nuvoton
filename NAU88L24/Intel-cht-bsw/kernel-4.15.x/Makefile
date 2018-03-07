KVER ?= `uname -r`
MDIR ?= /lib/modules/$(KVER)
KDIR ?= $(MDIR)/build

default:
	$(MAKE) -C $(KDIR) M=$$PWD

install:
	cp snd-soc-acpi-intel-match.ko $(MDIR)/kernel/sound/soc/intel/common
	cp snd-soc-sst-cht-bsw-nau8824.ko $(MDIR)/kernel/sound/soc/intel/boards
	depmod -a $(KVER)

ucm:
	rm -rf /usr/share/alsa/ucm/chtnau8824
	cp -R ./chtnau8824 /usr/share/alsa/ucm/

clean:
	rm -f *.ko *.o *.mod.* *.xz
