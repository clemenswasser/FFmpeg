add_library(swresample)
target_link_libraries(swresample PRIVATE ffmpeg_defaults)
target_sources(swresample PRIVATE
    audioconvert.c
    dither.c
    options.c
    resample_dsp.c
    rematrix.c
    swresample.c
    resample.c
    x86/audio_convert.asm
    x86/rematrix.asm
    x86/resample.asm
    swresample_frame.c
    version.c
    x86/audio_convert_init.c
    x86/resample_init.c
    x86/rematrix_init.c)