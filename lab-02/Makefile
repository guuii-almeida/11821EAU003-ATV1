CC = arm-none-eabi-gcc
CFLAGS = -c -mcpu=cortex-m4 -mthumb

main.o: main.c
	$(CC) $(CFLAGS) $< -o $@
clean:
	rm -f *.o