c_library('deck',
  sources = [
    'api/deck_analog.c',
    'api/deck_constants.c',
    'api/deck_digital.c',
  ],
  deps = [
    '//config:stm32',
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
