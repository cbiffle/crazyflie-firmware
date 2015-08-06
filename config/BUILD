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
