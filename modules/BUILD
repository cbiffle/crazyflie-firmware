c_library('headers',
  using = {
    'c_flags': [ '-I %(ROOT)s/modules/interface' ],
  },
)

c_library('log_decl',
  deps = [ ':headers' ],
)

c_library('param_decl',
  deps = [ ':headers' ],
)

