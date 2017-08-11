#
# Copyright (c) 2015 Liviu Ionescu.
# This file is part of the xPacks project (https://xpacks.github.io).
#
# Cross compile the CMSIS Core files with GCC.
#
# Input: (must be set by the caller)
#   PARENT=project root folder
#   TEST_NAME=test name
#

include arm-none-eabi.mk

DEFINES=-DSTM32F103xx

SRCS=\
stm32f1xx_hal.c \
stm32f1xx_hal_adc.c \
stm32f1xx_hal_adc_ex.c \
stm32f1xx_hal_can.c \
stm32f1xx_hal_cec.c \
stm32f1xx_hal_cortex.c \
stm32f1xx_hal_crc.c \
stm32f1xx_hal_dac.c \
stm32f1xx_hal_dac_ex.c \
stm32f1xx_hal_dma.c \
stm32f1xx_hal_eth.c \
stm32f1xx_hal_flash.c \
stm32f1xx_hal_flash_ex.c \
stm32f1xx_hal_gpio.c \
stm32f1xx_hal_gpio_ex.c \
stm32f1xx_hal_hcd.c \
stm32f1xx_hal_i2c.c \
stm32f1xx_hal_i2s.c \
stm32f1xx_hal_irda.c \
stm32f1xx_hal_iwdg.c \
stm32f1xx_hal_msp_template.c \
stm32f1xx_hal_nand.c \
stm32f1xx_hal_nor.c \
stm32f1xx_hal_pccard.c \
stm32f1xx_hal_pcd.c \
stm32f1xx_hal_pcd_ex.c \
stm32f1xx_hal_pwr.c \
stm32f1xx_hal_rcc.c \
stm32f1xx_hal_rcc_ex.c \
stm32f1xx_hal_rtc.c \
stm32f1xx_hal_rtc_ex.c \
stm32f1xx_hal_sd.c \
stm32f1xx_hal_smartcard.c \
stm32f1xx_hal_spi.c \
stm32f1xx_hal_spi_ex.c \
stm32f1xx_hal_sram.c \
stm32f1xx_hal_tim.c \
stm32f1xx_hal_tim_ex.c \
stm32f1xx_hal_uart.c \
stm32f1xx_hal_usart.c \
stm32f1xx_hal_wwdg.c \
stm32f1xx_ll_fsmc.c \
stm32f1xx_ll_sdmmc.c \
stm32f1xx_ll_usb.c

OBJS=$(SRCS:.c=.o)

CNOWARNFLAGS= -Wno-unused-parameter -Wno-conversion -Wno-missing-prototypes -Wno-missing-declarations -Wno-sign-compare -Wno-unused-but-set-variable -Wno-unused-variable -Wno-bad-function-cast

all:			srcs hal.elf

hal.elf:		$(OBJS) main.o config.o
	$(CC) $(CFLAGS) -Wl,-Map,"$(@:.elf=.map)" -o "$@" $(OBJS) config.o main.o
	arm-none-eabi-size --format=berkeley "hal.elf"
	
srcs:
	cp -r "$(PARENT)/Drivers/STM32F1xx_HAL_Driver/Src"/* .

main.o:			main.c

config.o:		config.c

%.o:
	$(CC) $(CPU) $(DEFINES) $(CFLAGS) $(WARNFLAGS) $(CWARNFLAGS) $(CNOWARNFLAGS) $(INCLUDES) -c -o "$@" "$(@:.o=.c)"


.PHONY:			all srcs

	