cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11 -frtti -DCC_ENABLE_CHIPMUNK_INTEGRATION=1  -fsigned-char")
set(cocos_dir /Users/oleh/Documents/tools/cocos2d-x-3.16)

set(SOURCES
           main.cpp
           AppDelegate.cpp
           HelloWorldScene.cpp)


include_directories( .

  ${cocos_dir}
  ${cocos_dir}/cocos
  ${cocos_dir}/cocos/audio/include
  ${cocos_dir}/deprecated
  ${cocos_dir}/external
  ${cocos_dir}/cocos/platform
  ${cocos_dir}/extensions
)

set(abi armeabi-v7a)
 ADD_DEFINITIONS (-DUSE_FILE32API)

add_library(MyGame SHARED
            ${SOURCES})




set(wholelib ${cocos_dir}/prebuilt/android/${abi}/libcocos2dxinternal.a
             ${cocos_dir}/prebuilt/android/${abi}/libcocos2dandroid.a
             ${cocos_dir}/prebuilt/android/${abi}/libaudioengine.a)





target_link_libraries(  MyGame
                        android
                        GLESv1_CM
                        GLESv2
                        log
                        EGL
                        OpenSLES

 -Wl,-whole-archive    ${wholelib}   -Wl,-no-whole-archive
                        ${cocos_dir}/prebuilt/android/${abi}/librecast.a
                        ${cocos_dir}/prebuilt/android/${abi}/libcocosdenshion.a
                        ${cocos_dir}/prebuilt/android/${abi}/libcpufeatures.a
                        ${cocos_dir}/prebuilt/android/${abi}/flatbuffers.a
                        ${cocos_dir}/prebuilt/android/${abi}/libcocos3d.a
                        ${cocos_dir}/prebuilt/android/${abi}/libcocosbuilder.a
                        ${cocos_dir}/prebuilt/android/${abi}/libcocostudio.a
                        ${cocos_dir}/prebuilt/android/${abi}/libpvmp3dec.a
                        ${cocos_dir}/prebuilt/android/${abi}/libspine.a
                        ${cocos_dir}/prebuilt/android/${abi}/libui.a
                        ${cocos_dir}/prebuilt/android/${abi}/libvorbisidec.a
                        ${cocos_dir}/prebuilt/android/${abi}/libcocosdenshion.a
                        ${cocos_dir}/prebuilt/android/${abi}/flatbuffers.a
                        ${cocos_dir}/prebuilt/android/${abi}/libcocos3d.a
                        ${cocos_dir}/prebuilt/android/${abi}/libcocosbuilder.a
                        ${cocos_dir}/prebuilt/android/${abi}/libcocostudio.a
                        ${cocos_dir}/prebuilt/android/${abi}/libpvmp3dec.a
                        ${cocos_dir}/prebuilt/android/${abi}/libspine.a
                        ${cocos_dir}/prebuilt/android/${abi}/libui.a
                        ${cocos_dir}/prebuilt/android/${abi}/libvorbisidec.a
                        ${cocos_dir}/prebuilt/android/${abi}/libextension.a
                        ${cocos_dir}/prebuilt/android/${abi}/libbox2d.a
                        ${cocos_dir}/prebuilt/android/${abi}/libnetwork.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libBulletCollision.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libBulletDynamics.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libBulletMultiThreaded.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libMiniCL.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libLinearMath.a
                        ${cocos_dir}/external/openssl/prebuilt/android/${abi}/libcrypto.a
                        ${cocos_dir}/external/freetype2/prebuilt/android/${abi}/libfreetype.a
                        ${cocos_dir}/external/png/prebuilt/android/${abi}/libpng.a
                        ${cocos_dir}/external/jpeg/prebuilt/android/${abi}/libjpeg.a
                        ${cocos_dir}/external/tiff/prebuilt/android/${abi}/libtiff.a
                        ${cocos_dir}/external/webp/prebuilt/android/${abi}/libwebp.a
                        ${cocos_dir}/external/chipmunk/prebuilt/android/${abi}/libchipmunk.a
                        ${cocos_dir}/external/zlib/prebuilt/android/${abi}/libz.a
                        ${cocos_dir}/external/openssl/prebuilt/android/${abi}/libssl.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libBulletCollision.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libBulletDynamics.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libBulletMultiThreaded.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libMiniCL.a
                        ${cocos_dir}/external/bullet/prebuilt/android/${abi}/libLinearMath.a
                        ${cocos_dir}/external/openssl/prebuilt/android/${abi}/libcrypto.a
                      )