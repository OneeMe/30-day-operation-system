
# 默认动作

default :
	make img

# 镜像文件生成

ipl.bin : ipl.nas Makefile
	nasm ipl.nas -o ipl.bin -l ipl.lst

helloos.img : ipl.bin Makefile
	dd of=helloos.img if=ipl.bin bs=512

# 其他指令

asm :
	make -r ipl.bin

img :
	make -r helloos.img

run :
	make img
	qemu-system-i386 helloos.img

clean :
	rm -rf ipl.bin
	rm -rf ipl.lst

src_only :
	make clean
	rm -rf helloos.img
