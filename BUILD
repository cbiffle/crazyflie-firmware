# Cobble notes:
# - Make build: 11.049s
# - Make -j build: 5.566s
# - Cobble build: 4.508s
#
# Touch config/config.h and rebuild:
# make -j: 3.345
# cobble: 2.681



includes = [
  'config',
  'platform',

  'drivers/interface',
  'hal/interface',
  'modules/interface',
  'utils/interface',
]

c_library('cf2lib',

  sources = [
    'init/main.c',

    'platform/%(platform)s/platform_%(platform)s.c',

    'hal/src/freeRTOSdebug.c',

    'hal/src/imu_%(platform)s.c',
    'hal/src/ledseq.c',
    'hal/src/ow_syslink.c',
    'hal/src/pm_%(processor)s.c',
    'hal/src/radiolink.c',
    'hal/src/syslink.c',
    'hal/src/usb_bsp.c',
    'hal/src/usb.c',
    'hal/src/usbd_desc.c',
    'hal/src/usblink.c',

    'utils/src/configblockeeprom.c',

    'modules/src/commander.c',
    'modules/src/comm.c',
    'modules/src/console.c',
    'modules/src/controller.c',
    'modules/src/crtp.c',
    'modules/src/crtpservice.c',
    'modules/src/expbrd.c',
    'modules/src/exptest.c',
    'modules/src/log.c',
    'modules/src/mem.c',
    'modules/src/neopixelring.c',
    'modules/src/param.c',
    'modules/src/pid.c',
    'modules/src/platformservice.c',
    'modules/src/sensfusion6.c',
    'modules/src/stabilizer.c',
    'modules/src/system.c',
    'modules/src/worker.c',

    'drivers/src/ak8963.c',
    'drivers/src/eeprom.c',
    'drivers/src/i2cdev_%(processor)s.c',
    'drivers/src/lps25h.c',
    'drivers/src/motors.c',
    'drivers/src/mpu6500.c',
    'drivers/src/nvic.c',
    'drivers/src/uart_syslink.c',
    'drivers/src/ws2812.c',
  ],

  deps = [
    '//lib/CMSIS',
    '//lib/STM32F4xx_StdPeriph_Driver',
    '//lib/FreeRTOS',
    '//lib/STM32_CPAL_Driver',
    '//lib/STM32_USB_OTG_Driver',
    '//lib/STM32_USB_Device_Library',
    '//deck',
    '//utils:cfassert',
    '//utils:core',
    '//utils:version',
    '//drivers:led',
    '//drivers:maxsonar',
  ],
)

c_binary('cf2',
  environment = 'cf2',
  deps = [
    ':cf2lib',
    '//lib/CMSIS:startup',
  ],
  extra = {
    'c_flags': ['-I %(ROOT)s/' + inc for inc in includes],
  },
)
