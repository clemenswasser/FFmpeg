add_library(postproc)
target_link_libraries(postproc PRIVATE ffmpeg_defaults)
target_sources(postproc PRIVATE postprocess.c version.c)