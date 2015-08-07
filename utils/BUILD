c_library('utils_headers',
  using = {
    'c_flags': [ '-I %(ROOT)s/utils/interface' ],
  },
)

c_library('cfassert',
  sources = [
    'src/cfassert.c',
  ],
  deps = [
    ':utils_headers',
    '//drivers:led',
  ],
)

c_library('core',
  sources = [
    'src/crc.c',
    'src/eprintf.c',
    'src/filter.c',
    'src/fp16.c',
  ],
  deps = [ ':utils_headers' ],
)

c_library('version',  # HACK
  sources = [
    'src/version.c',
  ],
  deps = [ ':utils_headers' ],
) 

c_library('configblockeeprom',
  sources = [
    'src/configblockeeprom.c',
  ],
  deps = [
    ':utils_headers',
    '//config:stm32',
    '//drivers:eeprom',
    '//drivers:i2c',
  ],
)
