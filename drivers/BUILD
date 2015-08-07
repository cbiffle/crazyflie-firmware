c_library('headers',
  using = {
    'c_flags': [
      '-I %(ROOT)s/drivers/interface',
    ],
  },
)

c_library('led',
  sources = [
    'src/led_%(processor)s.c',
  ],
  deps = [
    ':headers',
    '//lib/CMSIS',
    '//lib/FreeRTOS',
  ],
)

c_library('maxsonar',
  sources = [
    'src/maxsonar.c',
  ],
  deps = [
    ':headers',
    '//modules:log_decl',
    '//deck',
  ],
)

c_library('i2c',
  sources = [
    'src/i2cdev_%(processor)s.c',
  ],
  deps = [
    ':headers',
    '//lib/FreeRTOS',
    '//lib/CMSIS',
    '//lib/STM32_CPAL_Driver',
  ],
)

c_library('eeprom',
  sources = [
    'src/eeprom.c',
  ],
  deps = [
    ':headers',
    ':i2c',
    '//lib/FreeRTOS',
    '//utils:core',
  ],
)

c_library('ws2812',
  sources = [ 'src/ws2812.c' ],
  deps = [
    ':headers',
    '//lib/CMSIS',
    '//lib/FreeRTOS',
  ],
)
