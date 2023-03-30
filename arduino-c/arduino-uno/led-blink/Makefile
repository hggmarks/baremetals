default:
	avr-gcc -Os -DF_CPU=16000000UL -mmcu=atmega328p -c -o led-blink.o led-blink.c

	avr-gcc -o led-blink.bin led-blink.o
	avr-objcopy -O ihex -R .eeprom led-blink.bin led-blink.hex

	avrdude -F -V -c arduino -p ATMEGA328P -P /dev/ttyACM0 -b 115200 -U flash:w:led-blink.hex
