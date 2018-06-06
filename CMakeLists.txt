#include(${STIMSDK_INSTALL_DIR}/stimsdk.cmake)

set(BOARD nrf52_pca10040)
set(ZEPHYR_TOOLCHAIN_VARIANT "zephyr")

find_path(ZEPHYR_SDK_INSTALL_DIR sdk_version
    PATHS
    $ENV{HOME}/zephyr-sdk
    /opt/zephyr-sdk
    DOC "absolute path of sdk_version file ex: /installed/path/sdk_version"
    NO_DEFAULT_PATH
    )

set(CONF_FILE "${CMAKE_CURRENT_SOURCE_DIR}/prj.conf")

include($ENV{ZEPHYR_BASE}/cmake/app/boilerplate.cmake NO_POLICY_SCOPE)
project(NONE)

target_sources(app
    PRIVATE
        main.c)
