cmake_minimum_required(VERSION 3.4.1)

set (pvmp3_sources
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_normalize.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_alias_reduction.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_crc.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_decode_header.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_decode_huff_cw.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_getbits.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_dequantize_sample.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_framedecoder.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_get_main_data_size.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_get_side_info.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_get_scale_factors.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_mpeg2_get_scale_data.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_mpeg2_get_scale_factors.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_mpeg2_stereo_proc.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_huffman_decoding.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_huffman_parsing.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_tables.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_imdct_synth.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_mdct_6.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_dct_6.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_poly_phase_synthesis.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_equalizer.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_seek_synch.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_stereo_proc.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_reorder.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_polyphase_filter_window.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_mdct_18.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_dct_9.cpp
	../external/av/media/libstagefright/codecs/mp3dec/src/pvmp3_dct_16.cpp
	)


add_library(pv_mp3_dec SHARED ${pvmp3_sources})

target_include_directories(pv_mp3_dec PRIVATE ../external/av/media/libstagefright/codecs/mp3dec/include
       					../external/av/media/libstagefright/codecs/mp3dec/src include)

target_compile_options(pv_mp3_dec PRIVATE "-DOSCL_UNUSED_ARG(x)=(void)(x)" -Werror)

#target_link_libraries(pv_mp3_dec PRIVATE log)

