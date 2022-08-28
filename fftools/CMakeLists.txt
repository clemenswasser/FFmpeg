add_executable(ffprobe ffprobe.c cmdutils.c opt_common.c)
target_link_libraries(ffprobe PRIVATE
    avcodec
    avdevice
    avfilter
    avformat
    avutil
    ffmpeg_defaults
    postproc
    swresample
    swscale)

add_executable(ffmpeg)
target_link_libraries(ffmpeg PRIVATE
    avcodec
    avdevice
    avfilter
    avformat
    avutil
    ffmpeg_defaults
    postproc
    swresample
    swscale)

if(WIN32)
    target_link_libraries(ffmpeg PRIVATE psapi.lib)
endif()

target_sources(ffmpeg PRIVATE
    ffmpeg_demux.c
    ffmpeg_filter.c
    ffmpeg_hw.c
    ffmpeg_mux.c
    ffmpeg_opt.c
    objpool.c
    sync_queue.c
    thread_queue.c
    cmdutils.c
    opt_common.c
    ffmpeg.c)