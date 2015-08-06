c_library('stm32',
  deps = [
    '//lib/CMSIS',
  ],
)

c_library('cmsis_conf',
  using = {
    'c_flags': [ '-I %(ROOT)s/config' ],
  },
)

c_library('FreeRTOSConfig',
  using = {
    'c_flags': [ '-I %(ROOT)s/config' ],
    'link_flags': [
      # Hackishly resolve cycle between FreeRTOS and utils/cfassert
      '-u assertFail',
    ],
  },
)
