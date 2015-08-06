c_flags = [
  '-I %(ROOT)s/lib/STM32F4xx_StdPeriph_Driver/inc',
]

c_library('STM32F4xx_StdPeriph_Driver',
  sources = [
    'src/stm32f4xx_adc.c',
    'src/stm32f4xx_dbgmcu.c',
    'src/stm32f4xx_dma.c',
    'src/stm32f4xx_exti.c',
    'src/stm32f4xx_gpio.c',
    'src/stm32f4xx_i2c.c',
    'src/stm32f4xx_misc.c',
    'src/stm32f4xx_rcc.c',
    'src/stm32f4xx_tim.c',
    'src/stm32f4xx_usart.c',
  ],
  local = {
    'c_flags': c_flags,
  },
  using = {
    'c_flags': c_flags,
  },
  deps = [
    '//lib/CMSIS',
  ],
)
