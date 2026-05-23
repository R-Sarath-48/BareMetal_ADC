# STM32 ADC Register-Level Programming (Embedded C)

A bare-metal STM32 ADC implementation using direct register-level programming in Embedded C without using HAL libraries. This project demonstrates ADC initialization and analog data acquisition using memory-mapped registers on an STM32 microcontroller.


## Overview

This project configures **ADC1** on an STM32 microcontroller and continuously reads analog input values from **PA1 (ADC Channel 1)**. The converted ADC value is printed using `printf()` for monitoring and debugging.

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


## Working Principle

1. Enable clock access for GPIOA and ADC1.
2. Configure PA1 as Analog mode.
3. Select ADC Channel 1.
4. Enable ADC peripheral.
5. Start ADC conversion.
6. Wait for conversion completion.
7. Read digital value from ADC Data Register.
8. Print ADC value continuously.
