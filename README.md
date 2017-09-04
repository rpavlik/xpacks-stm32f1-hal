# STM32F1 HAL

This project, available from [GitHub](https://github.com/rpavlik/xpacks-stm32f1-hal),
includes the STM32F1 HAL files.

## Version

* ST HAL v1.1.1
* From STM32CubeMX HAL firmware bundle v1.6.0

## Documentation

The latest STM documentation is available from
[STM32CubeF1](http://www.st.com/en/embedded-software/stm32cubef1.html).

The latest CMSIS documentation is available from
[keil.com](http://www.keil.com/cmsis).

The list of latest packs is available from [keil.com](https://www.keil.com/dd2/pack/).

## Original files

The original files are available in the `originals` branch.

These files were extracted from `stm32cube_fw_f1_v160.zip`.

To save space, only the following folders were preserved:

* Drivers/STM32F\?xx\_HAL\_Driver/

and the following files were removed:

* Drivers/STM32F\?xx\_HAL\_Driver/*.chm

## Changes

* `Drivers/STM32F1xx\_HAL\_Driver/Src/stm32f1xx_ll_utils.c` - changed conditional include used when `USE_FULL_ASSERT` is defined, from `stm32_assert.h` to `stm32f1xx_hal_conf.h` (where it's typically defined)


