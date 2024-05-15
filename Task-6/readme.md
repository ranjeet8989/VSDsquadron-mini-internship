# Led blinking project on VSDSquadron Mini board :

1. Overview :-
   
   <p style="text-align: justify;">
   The goal of this project is to make an LED blink on the VSD Squadron Mini Debugger Board. This involves setting up the board, writing a simple program to control an LED,
   compiling the program, and uploading it to the board using OpenOCD.
   </p>

2. Components Required :-

- VSD Squadron Mini Debugger Board
- USB cable
- Development environment (RISC-V GCC toolchain, OpenOCD)

3. Steps Required for Hardware setup:-

   **Setup the Development Environment**
   
  - Install RISC-V GCC Toolchain: Ensure you have the necessary compiler for RISC-V.
  - Install OpenOCD: This is used for flashing the program to the board.
  - Drivers: Ensure you have the correct USB drivers installed for your operating system.

    **Hardware Setup**

  - Connect the LED to a GPIO pin on the VSD Squadron Mini Debugger Board .
  - Power the board via the USB cable.

4. Application code (C code ) for Led Blinking:-

```sh
#include <ch32v00x.h>
#include <debug.h>

#define BLINKY_GPIO_PORT GPIOD
#define BLINKY_GPIO_PIN GPIO_Pin_6
#define BLINKY_CLOCK_ENABLE RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE)

void NMI_Handler(void) __attribute__((interrupt("WCH-Interrupt-fast")));
void HardFault_Handler(void) __attribute__((interrupt("WCH-Interrupt-fast")));
void Delay_Init(void);
void Delay_Ms(uint32_t n);

int main(void)
{
	NVIC_PriorityGroupConfig(NVIC_PriorityGroup_2);
	SystemCoreClockUpdate();
	Delay_Init();

	GPIO_InitTypeDef GPIO_InitStructure = {0};

	BLINKY_CLOCK_ENABLE;
	GPIO_InitStructure.GPIO_Pin = BLINKY_GPIO_PIN;
	GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
	GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
	GPIO_Init(BLINKY_GPIO_PORT, &GPIO_InitStructure);

	uint8_t ledState = 0;
	while (1)
	{
		GPIO_WriteBit(BLINKY_GPIO_PORT, BLINKY_GPIO_PIN, ledState);
		ledState ^= 1; // invert for the next run
		Delay_Ms(3000);
	}
}

void NMI_Handler(void) {}
void HardFault_Handler(void)
{
	while (1)
	{
	}
}
   ```

5. Led Blinking Video

   https://drive.google.com/drive/u/0/folders/1SaBz9WaXcjdF0bklpkkaUuGQpa2vX_32
