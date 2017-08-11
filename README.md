# STM32F1 HAL

This project, available from [GitHub](https://github.com/rpavlik/stm32f1-hal),
includes the STM32F1 HAL files.

The "meta" content to make an xPack out of this is based on
the [STM32F4 HAL](https://github.com/xPacks/stm32f4-hal)

## Version

* ST HAL v1.4.0

## Documentation

The latest STM documentation is available from
[STM32CubeF1](http://www.st.com/en/embedded-software/stm32cubef1.html).

The latest CMSIS documentation is available from
[keil.com](http://www.keil.com/cmsis).

The list of latest packs is available from [keil.com](https://www.keil.com/dd2/pack/).

## Original files

The original files are available in the `originals` branch.

These files were extracted from `STM32Cube_FW_F1_V1.4.0`.

To save space, only the following folders were preserved:

* Drivers/STM32F\?xx\_HAL\_Driver/

## Changes

* None yet.

## Warnings

To silence warnings when compiling the HAL drivers, at least on F4, use:

```
-Wno-sign-conversion -Wno-padded -Wno-conversion -Wno-unused-parameter \
-Wno-bad-function-cast -Wno-sign-compare
```

## Tests

```
export PATH=/usr/local/gcc-arm-none-eabi-5_2-2015q4/bin:$PATH
bash ../../../scripts/run-tests.sh
```
