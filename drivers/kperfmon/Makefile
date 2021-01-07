#
# Makefile for the Linux kernel device drivers.
#
# Sep 2018, Binse Park <h22yap@gmail.com>
# Rewritten to use lists instead of if-statements.
#

FLAG=0

<<<<<<< HEAD
$(info kperfmon_DUMMY="$(shell cp -f $(srctree)/../../frameworks/base/proto/src/olog.proto  $(srctree)/drivers/kperfmon/)")
$(info kperfmon_DUMMY="$(shell cp -f $(srctree)/../../vendor/samsung/system/libperflog/aprotoc  $(srctree)/drivers/kperfmon/)")
$(info kperfmon_DUMMY="$(shell chmod 777 $(srctree)/drivers/kperfmon/aprotoc)")
$(info kperfmon_DUMMY="$(shell $(srctree)/drivers/kperfmon/aprotoc --perflog_out=./  $(srctree)/drivers/kperfmon/olog.proto)")
$(info kperfmon_DUMMY="$(shell cp -f $(srctree)/drivers/kperfmon/olog.pb.h  $(srctree)/include/linux/)")
#$(info kperfmon_DUMMY="$(shell ls $(srctree)/drivers/kperfmon/*)")
#$(info kperfmon_DUMMY="$(shell ls $(srctree)/include/linux/olog*)")
=======
ifeq ($(CONFIG_KPERFMON), y)
FLAG=1
endif
>>>>>>> Cruel/cruel-DTJA-v3.10

ifeq ($(FLAG), 1)
ifneq ($(shell [ -e $(srctree)/include/linux/olog.pb.h ] && echo exist), exist)
FLAG=0
$(warning "kperfmon: olog.pb.h file is missing.")
endif

ifneq ($(shell [ -e $(srctree)/include/linux/perflog.h ] && echo exist), exist)
FLAG=0
$(warning "kperfmon: perflog.h file is missing.")
endif
endif

ifeq ($(FLAG), 1)
	obj-y				+= kperfmon.o
else
	obj-y				+= ologk.o
endif
