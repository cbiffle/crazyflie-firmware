c_library('STM32_USB_OTG_Driver',
  sources = [
    'src/usb_core.c',
    'src/usb_dcd.c',
  ],
  deps = [
    ':headers',
    '//lib/CMSIS',
    '//hal:usb_conf',
  ],
  using = {
    'link_flags': [
      # Cycle to hal/src/usb_bsp.c
      '-u USB_OTG_BSP_mDelay',
    ],
  },
)

c_library('headers',
  using = {
    'c_flags': [
      '-I %(ROOT)s/lib/STM32_USB_OTG_Driver/inc',
    ],
  },
)
