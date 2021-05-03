mbr.bin: mbr.S
	- rm mbr.bin
	nasm -o mbr.bin mbr.S
hd60M.img: mbr.bin
	- rm hd60M.img
	bximage -hd=60M -mode="create" -q hd60M.img
	dd if=mbr.bin of=hd60M.img bs=512 count=1 conv=notrunc
run: hd60M.img
	bochs -f bochsrc.disk
