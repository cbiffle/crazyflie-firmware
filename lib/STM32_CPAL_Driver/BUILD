c_library('headers',
  using = {
    'c_flags': [
      '-I %(ROOT)s/lib/STM32_CPAL_Driver/inc',
    ],
  },
).extend_when(lambda e: e.get('processor') == 'f405',
  using = {
    'c_flags': [
      '-I %(ROOT)s/lib/STM32_CPAL_Driver/devices/stm32f4xx',
    ],
  },
)

c_library('STM32_CPAL_Driver',
  sources = [
    'src/cpal_hal.c',
    'src/cpal_i2c.c',
    'src/cpal_usercallback_template.c',  # apparently edited in-place
  ],
  deps = [
    ':headers',
    '//lib/CMSIS',
  ],
).extend_when(lambda e: e.get('processor') == 'f405',
  sources = [
    'devices/stm32f4xx/cpal_i2c_hal_stm32f4xx.c',
  ],
)
