c_library('FreeRTOS',
  sources = [
    'list.c',
    'queue.c',
    'tasks.c',
    'timers.c',

    'portable/%(freertos_port)s/port.c',

    'portable/MemMang/heap_4.c',
  ],
  deps = [
    '//config:FreeRTOSConfig',
  ],
  using = {
    'c_flags': [
      '-I %(ROOT)s/lib/FreeRTOS/include',
      '-I %(ROOT)s/lib/FreeRTOS/portable/%(freertos_port)s',
    ],
    'link_flags': [
      '-u vApplicationMallocFailedHook',
      '-u vApplicationStackOverflowHook',
    ],
  },
  local = {
    'c_flags': [
      '-I %(ROOT)s/lib/FreeRTOS/include',
      '-I %(ROOT)s/lib/FreeRTOS/portable/%(freertos_port)s',
    ],
  },
)
