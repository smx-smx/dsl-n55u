#
# Makefile for USB Core files and filesystem
#

usbcore-objs	:= usb.o hub.o hcd.o urb.o message.o driver.o \
			config.o file.o buffer.o sysfs.o endpoint.o \
			devio.o notify.o generic.o quirks.o

ifeq ($(CONFIG_PCI),y)
	usbcore-objs	+= hcd-pci.o
endif

ifeq ($(CONFIG_USB_DEVICEFS),y)
	usbcore-objs	+= inode.o devices.o
endif

obj-$(CONFIG_USB)	+= usbcore.o

ifeq ($(CONFIG_USB_DEBUG),y)
EXTRA_CFLAGS += -DDEBUG
endif
ifeq ($(CONFIG_USB_SERIAL_OPTION),m)
EXTRA_CFLAGS += -DTC_SUPPORT_3G
endif

ifeq ($(CONFIG_USB_SERIAL_OPTION),y)
EXTRA_CFLAGS += -DTC_SUPPORT_3G
endif
