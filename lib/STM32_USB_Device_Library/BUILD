c_library('STM32_USB_Device_Library',
  sources = [
    'Core/src/usbd_core.c',
    'Core/src/usbd_ioreq.c',
    'Core/src/usbd_req.c',
  ],
  deps = [
    ':headers',

    '//lib/STM32_USB_OTG_Driver',
    '//hal:usb_conf',
  ],
)

c_library('headers',
  using = {
    'c_flags': [
      '-I %(ROOT)s/lib/STM32_USB_Device_Library/Core/inc',
    ],
  },
)
