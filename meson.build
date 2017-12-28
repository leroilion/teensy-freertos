project('teensy-freertos', 'cpp')

assert(meson.is_cross_build(), 'Teensy projects can only be built in a cross build environment.')

teensy_core_dep = dependency('teensy-core',
    fallback: ['teensy-core', 'teensy_core_dep'])

teensy_freertos_incdir = include_directories('src/include', 'src/portable/GCC/ARM_CM4F/')
teensy_freertos_src = [
        'src/croutine.c',
        'src/event_groups.c',
        'src/list.c',
        'src/queue.c',
        'src/stream_buffer.c',
        'src/tasks.c',
        'src/timers.c',
        'src/portable/GCC/ARM_CM4F/port.c'
    ]

teensy_freertos = static_library('teensy-freertos',
        teensy_freertos_src,
        include_directories : teensy_freertos_incdir,
        dependencies : [teensy_core_dep]
    )

teensy_freertos_dep = declare_dependency(
        link_with : teensy_freertos,
        include_directories : teensy_freertos_incdir,
    )
