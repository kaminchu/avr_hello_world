# avr_hello_world

### 導入

必要なパッケージ
```
sudo apt-get install binutils-avr gcc-avr avr-libc avrdude
```

対応IC
```
avrdude -p ?
```

対応書き込み機
```
avrdude -c ?
```

### 書き込み(ATTiny85)

```
avr-gcc -Wall -Os -DF_CPU=1000000 -mmcu=attiny85 -o hello.o hello.c
avr-objcopy -j .text -j .data -O ihex hello.o hello.hex
avrdude -c usbasp -p t85 -U flash:w:hello.hex:i
```
