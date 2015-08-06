c_library('deck',
  sources = [
    'api/deck_analog.c',
    'api/deck_constants.c',
    'api/deck_digital.c',
  ],
  deps = [
    '//lib/CMSIS',
    '//lib/STM32F4xx_StdPeriph_Driver',
  ],
  local = {
    'c_flags': [
      '-I %(ROOT)s/deck/interface',
    ],
  },
  using = {
    'c_flags': [
      '-I %(ROOT)s/deck/interface',
    ],
  },
)
