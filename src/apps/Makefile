CC = gcc
CFLAGS = -m32 -nostdlib -nostdinc -fno-builtin -fno-stack-protector \
		 -nostartfiles -nodefaultlibs -Wall -Wextra -Werror \
		 -Wno-unused-function -c
AS = nasm
ASFLAGS = -f elf
LD = ld
LDFLAGS = -T link.ld -melf_i386
LIBC = -L../libc -lc
STDINCLUDE = -I../libc

init: init.o
	$(LD) $(LDFLAGS) init.o $(LIBC) -o init

%.o: %.c
	$(CC) $(CFLAGS) $(STDINCLUDE) $< -o $@

%.o: %.s
	$(AS) $(ASFLAGS) $< -o $@

clean:
	rm -rf init *.o