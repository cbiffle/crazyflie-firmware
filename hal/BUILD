c_library('usb_conf',
  deps = [ ':interface' ],
)

c_library('interface',
  using = {
    'c_flags': [
      '-I %(ROOT)s/hal/interface',
    ],
  },
)
