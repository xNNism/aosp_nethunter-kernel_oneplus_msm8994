# Makefile for the Linux sound card driver
#

ccflags-y ?=
ccflags-y += -O1 -fthread-jumps \
          -falign-functions -falign-jumps \
          -falign-loops -falign-labels \
          -fcse-follow-jumps -fcse-skip-blocks \
          -fexpensive-optimizations \
          -fgcse -fgcse-lm \
          -fhoist-adjacent-loads \
          -finline-small-functions \
          -findirect-inlining \
          -fipa-cp \
          -fipa-sra \
          -fisolate-erroneous-paths-dereference \
          -foptimize-sibling-calls \
          -foptimize-strlen \
          -fpeephole2 \
          -frerun-cse-after-loop \
          -fstrict-aliasing \
          -ftree-switch-conversion -ftree-tail-merge \
          -ftree-pre \
          -ftree-vrp \
          -mtune=cortex-a57.cortex-a53 \
-march=armv8-a+simd

obj-$(CONFIG_SOUND) += soundcore.o
obj-$(CONFIG_SOUND_PRIME) += sound_firmware.o
obj-$(CONFIG_SOUND_PRIME) += oss/
obj-$(CONFIG_DMASOUND) += oss/
obj-$(CONFIG_SND) += core/ i2c/ drivers/ isa/ pci/ ppc/ arm/ sh/ synth/ usb/ \
	firewire/ sparc/ spi/ parisc/ pcmcia/ mips/ soc/ atmel/
obj-$(CONFIG_SND_AOA) += aoa/

# This one must be compilable even if sound is configured out
obj-$(CONFIG_AC97_BUS) += ac97_bus.o

ifeq ($(CONFIG_SND),y)
  obj-y += last.o
endif

soundcore-objs  := sound_core.o
