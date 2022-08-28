add_executable(print_options print_options.c)
target_link_libraries(print_options PRIVATE ffmpeg_defaults)

add_custom_command(OUTPUT avoptions_format.texi COMMAND print_options format)
add_custom_command(OUTPUT avoptions_codec.texi COMMAND print_options codec)

find_package(Perl)

if(PERL_FOUND)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg.pod > ffmpeg.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe.pod > ffprobe.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-all.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-all.pod > ffmpeg-all.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-all.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe-all.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe-all.pod > ffprobe-all.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe-all.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-utils.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-utils.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-utils.pod > ffmpeg-utils.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-utils.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-utils.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-scaler.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-scaler.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-scaler.pod > ffmpeg-scaler.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-scaler.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-scaler.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-resampler.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-resampler.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-resampler.pod > ffmpeg-resampler.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-resampler.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-resampler.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-codecs.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-codecs.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-codecs.pod > ffmpeg-codecs.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-codecs.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-codecs.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-bitstream-filters.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-bitstream-filters.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-bitstream-filters.pod > ffmpeg-bitstream-filters.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-bitstream-filters.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-bitstream-filters.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-formats.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-formats.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-formats.pod > ffmpeg-formats.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-formats.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-formats.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-protocols.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-protocols.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-protocols.pod > ffmpeg-protocols.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-protocols.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-protocols.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-devices.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-devices.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-devices.pod > ffmpeg-devices.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-devices.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-devices.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-filters.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-filters.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-filters.pod > ffmpeg-filters.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-filters.texi ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-filters.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavutil.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/libavutil.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavutil.pod > libavutil.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/libavutil.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavutil.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libswscale.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/libswscale.texi ${CMAKE_CURRENT_SOURCE_DIR}/libswscale.pod > libswscale.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/libswscale.texi ${CMAKE_CURRENT_SOURCE_DIR}/libswscale.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libswresample.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/libswresample.texi ${CMAKE_CURRENT_SOURCE_DIR}/libswresample.pod > libswresample.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/libswresample.texi ${CMAKE_CURRENT_SOURCE_DIR}/libswresample.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavcodec.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/libavcodec.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavcodec.pod > libavcodec.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/libavcodec.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavcodec.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavformat.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/libavformat.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavformat.pod > libavformat.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/libavformat.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavformat.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavdevice.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/libavdevice.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavdevice.pod > libavdevice.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/libavdevice.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavdevice.pod)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavfilter.pod.d COMMAND
        ${PERL_EXECUTABLE} ./doc/texidep.pl . ${CMAKE_CURRENT_SOURCE_DIR}/libavfilter.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavfilter.pod > libavfilter.pod.d
        && ${PERL_EXECUTABLE} ./doc/texi2pod.pl -Dconfig-not-all=yes -I${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/libavfilter.texi ${CMAKE_CURRENT_SOURCE_DIR}/libavfilter.pod)
endif()

find_program(POD2MAN_EXECURTABLE NAMES pod2man)

if(POD2MAN_EXECURTABLE)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg.pod > ffmpeg.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe.pod > ffprobe.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-all.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-all.pod > ffmpeg-all.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe-all.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffprobe-all.pod > ffprobe-all.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-utils.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-utils.pod > ffmpeg-utils.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-scaler.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-scaler.pod > ffmpeg-scaler.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-resampler.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-resampler.pod > ffmpeg-resampler.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-codecs.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-codecs.pod > ffmpeg-codecs.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-bitstream-filters.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-bitstream-filters.pod > ffmpeg-bitstream-filters.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-formats.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-formats.pod > ffmpeg-formats.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-protocols.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-protocols.pod > ffmpeg-protocols.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-devices.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-devices.pod > ffmpeg-devices.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-filters.1 COMMAND
        pod2man --section=1 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/ffmpeg-filters.pod > ffmpeg-filters.1)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavutil.3 COMMAND
        pod2man --section=3 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/libavutil.pod > libavutil.3)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libswscale.3 COMMAND
        pod2man --section=3 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/libswscale.pod > libswscale.3)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libswresample.3 COMMAND
        pod2man --section=3 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/libswresample.pod > libswresample.3)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavcodec.3 COMMAND
        pod2man --section=3 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/libavcodec.pod > libavcodec.3)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavformat.3 COMMAND
        pod2man --section=3 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/libavformat.pod > libavformat.3)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavdevice.3 COMMAND
        pod2man --section=3 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/libavdevice.pod > libavdevice.3)
    add_custom_command(OUTPUT ${CMAKE_CURRENT_SOURCE_DIR}/libavfilter.3 COMMAND
        pod2man --section=3 --center=" " --release=" " --date=" " ${CMAKE_CURRENT_SOURCE_DIR}/libavfilter.pod > libavfilter.3)
endif()