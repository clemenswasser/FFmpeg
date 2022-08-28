include(CMakeDependentOption)
cmake_dependent_option(AV_HAVE_BIGENDIAN "" "1" "CMAKE_C_BYTE_ORDER STREQUAL BIG_ENDIAN" "0")

string(CONCAT AV_CONFIG_H_CONTENT
    "#ifndef AVUTIL_AVCONFIG_H\n"
    "#define AVUTIL_AVCONFIG_H\n"
    "#define AV_HAVE_BIGENDIAN ${AV_HAVE_BIGENDIAN}\n"
    "#define AV_HAVE_FAST_UNALIGNED 1\n"
    "#endif /* AVUTIL_AVCONFIG_H */\n")
file(GENERATE OUTPUT avconfig.h CONTENT ${AV_CONFIG_H_CONTENT})

add_library(avutil)
target_link_libraries(avutil PRIVATE ffmpeg_defaults bcrypt.lib)
target_sources(avutil PRIVATE
    adler32.c
    aes.c
    aes_ctr.c
    audio_fifo.c
    avsscanf.c
    avstring.c
    base64.c
    blowfish.c
    bprint.c
    buffer.c
    camellia.c
    cast5.c
    channel_layout.c
    color_utils.c
    cpu.c
    crc.c
    csp.c
    des.c
    detection_bbox.c
    dict.c
    display.c
    dovi_meta.c
    downmix_info.c
    encryption_info.c
    error.c
    eval.c
    fifo.c
    file.c
    file_open.c
    film_grain_params.c
    fixed_dsp.c
    float_dsp.c
    frame.c
    hash.c
    hdr_dynamic_metadata.c
    hdr_dynamic_vivid_metadata.c
    hmac.c
    hwcontext.c
    hwcontext_d3d11va.c
    hwcontext_dxva2.c
    hwcontext_stub.c
    imgutils.c
    integer.c
    intmath.c
    lfg.c
    lls.c
    log.c
    log2_tab.c
    lzo.c
    mastering_display_metadata.c
    mathematics.c
    md5.c
    mem.c
    murmur3.c
    opt.c
    parseutils.c
    pixdesc.c
    pixelutils.c
    random_seed.c
    rational.c
    rc4.c
    reverse.c
    ripemd.c
    samplefmt.c
    sha.c
    sha512.c
    slicethread.c
    spherical.c
    stereo3d.c
    tea.c
    threadmessage.c
    time.c
    timecode.c
    tree.c
    twofish.c
    tx.c
    tx_double.c
    tx_float.c
    tx_int32.c
    utils.c
    uuid.c
    version.c
    video_enc_params.c
    x86/cpu.c
    x86/cpuid.asm
    x86/emms.asm
    x86/fixed_dsp.asm
    x86/fixed_dsp_init.c
    x86/float_dsp.asm
    x86/float_dsp_init.c
    x86/imgutils.asm
    x86/imgutils_init.c
    x86/lls.asm
    x86/lls_init.c
    x86/pixelutils.asm
    x86/pixelutils_init.c
    x86/tx_float.asm
    x86/tx_float_init.c
    xga_font_data.c)