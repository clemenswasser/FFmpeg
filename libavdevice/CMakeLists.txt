add_library(avdevice)
target_link_libraries(avdevice PRIVATE ffmpeg_defaults)

if(WIN32)
    target_link_libraries(avdevice PRIVATE shlwapi.lib vfw32.lib)
endif()

target_sources(avdevice PRIVATE
    utils.c
    avdevice.c
    version.c
    alldevices.c
    dshow_enummediatypes.c
    dshow_common.c
    dshow_crossbar.c
    dshow.c
    dshow_filter.c
    dshow_enumpins.c
    dshow_pin.c
    file_open.c
    gdigrab.c
    lavfi.c
    vfwcap.c)