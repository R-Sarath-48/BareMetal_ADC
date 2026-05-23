# STM32 ADC Register-Level Programming (Embedded C)

A bare-metal STM32 ADC implementation using direct register-level programming in Embedded C without using HAL libraries. This project demonstrates ADC initialization and analog data acquisition using memory-mapped registers on an STM32 microcontroller.

---

## Overview

This project configures **ADC1** on an STM32 microcontroller and continuously reads analog input values from **PA1 (ADC Channel 1)**. The converted ADC value is printed using `printf()` for monitoring and debugging.

The project is focused on learning:

- Register-level programming
- STM32 peripheral configuration
- ADC operation
- Embedded C firmware development
- Bare-metal programming concepts

---

## Features

- Direct register manipulation
- ADC1 single-channel conversion
- Analog input reading from PA1
- Polling-based ADC conversion
- Lightweight firmware without HAL
- Beginner-friendly embedded implementation

---

## Hardware Requirements

- STM32 Development Board (STM32F4 recommended)
- Potentiometer or analog sensor
- USB-to-Serial converter (optional)
- Breadboard and jumper wires

---

## Software Requirements

- STM32CubeIDE / Keil µVision
- ARM GCC Toolchain
- Serial Monitor (optional for UART output)

---

## Pin Configuration

| Pin | Function |
|------|-----------|
| PA1 | ADC Channel 1 Input |

---

## Register Configuration

| Register | Purpose |
|----------|---------|
| AHB1ENR | Enable GPIOA clock |
| APB2ENR | Enable ADC1 clock |
| GPIOA_MODER | Configure PA1 as Analog |
| ADC1_CR2 | ADC control and conversion start |
| SQR3 | ADC channel selection |
| SR | ADC status register |
| DR | ADC converted data register |

---

## Working Principle

1. Enable clock access for GPIOA and ADC1.
2. Configure PA1 as Analog mode.
3. Select ADC Channel 1.
4. Enable ADC peripheral.
5. Start ADC conversion.
6. Wait for conversion completion.
7. Read digital value from ADC Data Register.
8. Print ADC value continuously.

---

## Code Snippet

```c
*ADC1_CR2 |= 0x40000000; // Start ADC conversion

while(!(*SR & 2)) {
}

AnalogValue = *DR;
```
---

## Author

**Sarath R**  
Embedded Systems & IoT Developer
- LinkedIn: https:[//linkedin.com/in/](https://www.linkedin.com/in/sarath-r-2005h/)

---

## License

This project is open-source and intended for educational and learning purposes.
