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

  'deck/interface',
  'drivers/interface',
  'hal/interface',
  'modules/interface',
  'utils/interface',
  
  'lib/FreeRTOS/include',
  'lib/FreeRTOS/portable/%(freertos_port)s',

  'lib/CMSIS/STM32F4xx/Include',
  'lib/CMSIS/Include',

  'lib/STM32F4xx_StdPeriph_Driver/inc',

  'lib/STM32_CPAL_Driver/inc',
  'lib/STM32_CPAL_Driver/devices/stm32f4xx',

  'lib/STM32_USB_Device_Library/Core/inc',
  'lib/STM32_USB_OTG_Driver/inc',
]

c_binary('cf2',
  environment = 'cf2',
  sources = [
    'lib/CMSIS/STM32F4xx/Source/startup_stm32f40xx.s',
    'lib/CMSIS/STM32F4xx/Source/system_stm32f4xx.c',

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

    'utils/src/cfassert.c',
    'utils/src/configblockeeprom.c',
    'utils/src/crc.c',
    'utils/src/eprintf.c',
    'utils/src/filter.c',
    'utils/src/fp16.c',

    'utils/src/version.c',

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

    'deck/api/deck_analog.c',
    'deck/api/deck_constants.c',
    'deck/api/deck_digital.c',

    'drivers/src/ak8963.c',
    'drivers/src/eeprom.c',
    'drivers/src/i2cdev_%(processor)s.c',
    'drivers/src/led_%(processor)s.c',
    'drivers/src/lps25h.c',
    'drivers/src/motors.c',
    'drivers/src/mpu6500.c',
    'drivers/src/nvic.c',
    'drivers/src/uart_syslink.c',
    'drivers/src/ws2812.c',

    'lib/FreeRTOS/list.c',
    'lib/FreeRTOS/queue.c',
    'lib/FreeRTOS/tasks.c',
    'lib/FreeRTOS/timers.c',

    'lib/FreeRTOS/portable/%(freertos_port)s/port.c',

    'lib/FreeRTOS/portable/MemMang/heap_4.c',

    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_adc.c',
    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_dbgmcu.c',
    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_dma.c',
    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_exti.c',
    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_gpio.c',
    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_i2c.c',
    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_misc.c',
    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_rcc.c',
    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_tim.c',
    'lib/STM32F4xx_StdPeriph_Driver/src/stm32f4xx_usart.c',

    'lib/STM32_CPAL_Driver/devices/stm32f4xx/cpal_i2c_hal_stm32f4xx.c',
    'lib/STM32_CPAL_Driver/src/cpal_hal.c',
    'lib/STM32_CPAL_Driver/src/cpal_i2c.c',
    'lib/STM32_CPAL_Driver/src/cpal_usercallback_template.c',

    'lib/STM32_USB_OTG_Driver/src/usb_core.c',
    'lib/STM32_USB_OTG_Driver/src/usb_dcd.c',

    'lib/STM32_USB_Device_Library/Core/src/usbd_core.c',
    'lib/STM32_USB_Device_Library/Core/src/usbd_ioreq.c',
    'lib/STM32_USB_Device_Library/Core/src/usbd_req.c',
  ],

  extra = {
    'c_flags': ['-I %(ROOT)s/' + inc for inc in includes] + [
      '-DSTM32F4XX',
      '-DSTM32F40_41xxx',
      '-DHSE_VALUE=8000000',
      '-DUSE_STDPERIPH_DRIVER',
    ],
  },

  local = {
    'link_flags': [
      '-nostartfiles',
      '-T %(ROOT)s/scripts/%(PROCESSOR)s/linker/FLASH_CLOAD.ld',
      '-L %(ROOT)s/scripts/%(PROCESSOR)s/linker',
    ],
  },
)
