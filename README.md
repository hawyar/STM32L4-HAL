### Blink LED:

```c
void Blink(uint32_t delay);
```

Blink with a 500ms delay

```c
Blink(500);
```

### Transmit Data

```c
void UART_Transmit(UART_HandleTypeDef *huart, uint8_t *data, uint16_t size);
```

Set USART1 to `Asynchronous` mode with:

- Baud Rate: 115200
- Data Bits: 8 (including parity)

Connect to the serial port with the set baud rate.

```bash
screen /dev/tty.usbmodem114203 115200
```

Now send data and the text should appear on the terminal.

```c
uint8_t data[] = "Ping!\r\n";
UART_Transmit(&huart1, data, sizeof(data));
```

Note:

- Add the `-u _printf_float` flag to the GCC linker.
