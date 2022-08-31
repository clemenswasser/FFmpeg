add_executable(checkasm)
target_link_libraries(checkasm PRIVATE ffmpeg_defaults avcodec avutil swresample avfilter)
target_sources(checkasm PRIVATE
    aacpsdsp.c
    af_afir.c
    alacdsp.c
    audiodsp.c
    av_tx.c
    blockdsp.c
    bswapdsp.c
    fixed_dsp.c
    flacdsp.c
    float_dsp.c
    g722dsp.c
    fmtconvert.c
    h264dsp.c
    h264pred.c
    checkasm.c
    h264qpel.c
    hevc_add_res.c
    hevc_idct.c
    hevc_pel.c
    hevc_sao.c
    huffyuvdsp.c
    idctdsp.c
    jpeg2000dsp.c
    llviddsp.c
    llviddspenc.c
    opusdsp.c
    motion.c
    pixblockdsp.c
    sbrdsp.c
    sw_rgb.c
    synth_filter.c
    utvideodsp.c
    sw_gbrp.c
    v210dec.c
    sw_scale.c
    v210enc.c
    vc1dsp.c
    vf_colorspace.c
    vf_gblur.c
    vf_blend.c
    x86/checkasm.asm
    vf_hflip.c
    vf_nlmeans.c
    vf_threshold.c
    videodsp.c
    vp8dsp.c
    vp9dsp.c)

set(FATE_RUN_SH ${ffmpeg_SOURCE_DIR}/tests/fate-run.sh)
add_test(NAME fate-checkasm-aacpsdsp COMMAND ${FATE_RUN_SH} fate-checkasm-aacpsdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=aacpsdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-af_afir COMMAND ${FATE_RUN_SH} fate-checkasm-af_afir "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=af_afir" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-alacdsp COMMAND ${FATE_RUN_SH} fate-checkasm-alacdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=alacdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-audiodsp COMMAND ${FATE_RUN_SH} fate-checkasm-audiodsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=audiodsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-av_tx COMMAND ${FATE_RUN_SH} fate-checkasm-av_tx "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=av_tx" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-blockdsp COMMAND ${FATE_RUN_SH} fate-checkasm-blockdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=blockdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-bswapdsp COMMAND ${FATE_RUN_SH} fate-checkasm-bswapdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=bswapdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-exrdsp COMMAND ${FATE_RUN_SH} fate-checkasm-exrdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=exrdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-fixed_dsp COMMAND ${FATE_RUN_SH} fate-checkasm-fixed_dsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=fixed_dsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-flacdsp COMMAND ${FATE_RUN_SH} fate-checkasm-flacdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=flacdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-float_dsp COMMAND ${FATE_RUN_SH} fate-checkasm-float_dsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=float_dsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-fmtconvert COMMAND ${FATE_RUN_SH} fate-checkasm-fmtconvert "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=fmtconvert" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-g722dsp COMMAND ${FATE_RUN_SH} fate-checkasm-g722dsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=g722dsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-h264dsp COMMAND ${FATE_RUN_SH} fate-checkasm-h264dsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=h264dsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-h264pred COMMAND ${FATE_RUN_SH} fate-checkasm-h264pred "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=h264pred" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-h264qpel COMMAND ${FATE_RUN_SH} fate-checkasm-h264qpel "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=h264qpel" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-hevc_add_res COMMAND ${FATE_RUN_SH} fate-checkasm-hevc_add_res "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=hevc_add_res" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-hevc_idct COMMAND ${FATE_RUN_SH} fate-checkasm-hevc_idct "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=hevc_idct" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-hevc_pel COMMAND ${FATE_RUN_SH} fate-checkasm-hevc_pel "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=hevc_pel" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-hevc_sao COMMAND ${FATE_RUN_SH} fate-checkasm-hevc_sao "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=hevc_sao" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-huffyuvdsp COMMAND ${FATE_RUN_SH} fate-checkasm-huffyuvdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=huffyuvdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-idctdsp COMMAND ${FATE_RUN_SH} fate-checkasm-idctdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=idctdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-jpeg2000dsp COMMAND ${FATE_RUN_SH} fate-checkasm-jpeg2000dsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=jpeg2000dsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-llviddsp COMMAND ${FATE_RUN_SH} fate-checkasm-llviddsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=llviddsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-llviddspenc COMMAND ${FATE_RUN_SH} fate-checkasm-llviddspenc "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=llviddspenc" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-motion COMMAND ${FATE_RUN_SH} fate-checkasm-motion "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=motion" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-opusdsp COMMAND ${FATE_RUN_SH} fate-checkasm-opusdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=opusdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-pixblockdsp COMMAND ${FATE_RUN_SH} fate-checkasm-pixblockdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=pixblockdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-sbrdsp COMMAND ${FATE_RUN_SH} fate-checkasm-sbrdsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=sbrdsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-synth_filter COMMAND ${FATE_RUN_SH} fate-checkasm-synth_filter "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=synth_filter" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-sw_gbrp COMMAND ${FATE_RUN_SH} fate-checkasm-sw_gbrp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=sw_gbrp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-sw_rgb COMMAND ${FATE_RUN_SH} fate-checkasm-sw_rgb "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=sw_rgb" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-sw_scale COMMAND ${FATE_RUN_SH} fate-checkasm-sw_scale "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=sw_scale" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-utvideodsp COMMAND ${FATE_RUN_SH} fate-checkasm-utvideodsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=utvideodsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-v210dec COMMAND ${FATE_RUN_SH} fate-checkasm-v210dec "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=v210dec" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-v210enc COMMAND ${FATE_RUN_SH} fate-checkasm-v210enc "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=v210enc" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vc1dsp COMMAND ${FATE_RUN_SH} fate-checkasm-vc1dsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vc1dsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vf_blend COMMAND ${FATE_RUN_SH} fate-checkasm-vf_blend "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vf_blend" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vf_colorspace COMMAND ${FATE_RUN_SH} fate-checkasm-vf_colorspace "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vf_colorspace" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vf_eq COMMAND ${FATE_RUN_SH} fate-checkasm-vf_eq "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vf_eq" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vf_gblur COMMAND ${FATE_RUN_SH} fate-checkasm-vf_gblur "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vf_gblur" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vf_hflip COMMAND ${FATE_RUN_SH} fate-checkasm-vf_hflip "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vf_hflip" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vf_nlmeans COMMAND ${FATE_RUN_SH} fate-checkasm-vf_nlmeans "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vf_nlmeans" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vf_threshold COMMAND ${FATE_RUN_SH} fate-checkasm-vf_threshold "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vf_threshold" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-videodsp COMMAND ${FATE_RUN_SH} fate-checkasm-videodsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=videodsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vp8dsp COMMAND ${FATE_RUN_SH} fate-checkasm-vp8dsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vp8dsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")
add_test(NAME fate-checkasm-vp9dsp COMMAND ${FATE_RUN_SH} fate-checkasm-vp9dsp "${ffmpeg_SOURCE_DIR}/fate-suite" "" "${ffmpeg_SOURCE_DIR}" "run $<TARGET_FILE:checkasm> --test=vp9dsp" "null" "" "" "1" "" "" "" "" "" "" "" "" "" "")