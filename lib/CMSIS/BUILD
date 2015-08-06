c_library('CMSIS',
  using = {
    'c_flags': [
      '-I %(ROOT)s/lib/CMSIS/Include',
    ],
  },
  deps = [
    '//config:cmsis_conf',
  ],
).extend_when(lambda e: e['processor'] == 'f405',
  using = {
    'c_flags': [
      '-I %(ROOT)s/lib/CMSIS/STM32F4xx/Include',
      '-I %(ROOT)s/lib/STM32F4xx_StdPeriph_Driver/inc',  # HACK
    ],
  },
)

c_library('startup',
  deps = [ ':CMSIS' ],
  using = {
    'link_flags': [ '-nostartfiles', '-u main' ],
  },
  local = {
    'whole_archive': True,
  },
).extend_when(lambda e: e['processor'] == 'f405',
  sources = [
    'STM32F4xx/Source/startup_stm32f40xx.s',
    'STM32F4xx/Source/system_stm32f4xx.c',
  ],
  deps = [
    '//lib/STM32F4xx_StdPeriph_Driver',
  ],
) 
