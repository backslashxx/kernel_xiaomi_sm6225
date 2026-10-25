# NOTE: unity build. single unit.

obj-$(CONFIG_FGETPRIORITY) += fgetpriority.o
fgetpriority-y := main.o

CFLAGS_fgetpriority.o +=  $(call cc-option, -std=gnu11)
CFLAGS_fgetpriority.o +=  $(call cc-option, -std=gnu17)
CFLAGS_fgetpriority.o +=  $(call cc-option, -std=gnu23)
CFLAGS_fgetpriority.o +=  $(call cc-option, -std=gnu2y)

CFLAGS_fgetpriority.o += -g0
CFLAGS_fgetpriority.o += $(call cc-option, -Wno-declaration-after-statement)
CFLAGS_fgetpriority.o += $(call cc-option, -Wno-deprecated-octal-literals)

ifeq ($(CONFIG_CC_OPTIMIZE_FOR_SIZE),y)
CFLAGS_REMOVE_fgetpriority.o += -Oz
CFLAGS_REMOVE_fgetpriority.o += -Os
CFLAGS_fgetpriority.o += -O2
endif

CFLAGS_REMOVE_fgetpriority.o += -fno-builtin

CFLAGS_fgetpriority.o += -g0 -fno-unwind-tables -fno-asynchronous-unwind-tables -fomit-frame-pointer
CFLAGS_fgetpriority.o += $(call cc-option, -momit-leaf-frame-pointer)

CFLAGS_REMOVE_fgetpriority.o += $(CC_FLAGS_FTRACE)
CFLAGS_REMOVE_fgetpriority.o += -pg

CFLAGS_REMOVE_fgetpriority.o += -ftrivial-auto-var-init=pattern
CFLAGS_REMOVE_fgetpriority.o += -ftrivial-auto-var-init=zero
CFLAGS_REMOVE_fgetpriority.o += -enable-trivial-auto-var-init-zero-knowing-it-will-be-removed-from-clang

# if cflags can be macro'd, this will be called 'TRUST_ME'
CFLAGS_fgetpriority.o += -fno-stack-protector -fno-stack-check
CFLAGS_REMOVE_fgetpriority.o += -fsanitize=shadow-call-stack
