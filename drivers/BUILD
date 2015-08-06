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
