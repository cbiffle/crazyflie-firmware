c_library('utils_headers',
  using = {
    'c_flags': [ '-I %(ROOT)s/utils/interface' ],
  },
)

c_library('eprintf',
  sources = [ 'src/eprintf.c' ],
  deps = [ ':utils_headers' ],
)
