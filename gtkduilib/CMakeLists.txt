find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)

set(SRC 
    compat.h
    DialogBuilder.cpp
    DialogBuilder.h
    NotifyPump.cpp
    NotifyPump.h
    pugiconfig.hpp
    pugixml.cpp
    pugixml.hpp
    ResourceMgr.cpp
    ResourceMgr.h
    stdafx.cpp
    stdafx.h
    UIButton.cpp
    UIButton.h
    UIChildLayout.cpp
    UIChildLayout.h
    UIContainer.cpp
    UIContainer.h
    UIControl.cpp
    UIControl.h
    UIDefine.h
    UIEvent.cpp
    UIEvent.h
    UIFont.cpp
    UIFont.h
    UIHorizontalLayout.cpp
    UIHorizontalLayout.h
    UILabel.cpp
    UILabel.h
    UILib.h
    UIList.cpp
    UIList.h
    UIOption.cpp
    UIOption.h
    UIProgress.cpp
    UIProgress.h
    UIRef.h
    UIRender.cpp
    UIRender.h
    UIScrollBar.cpp
    UIScrollBar.h
    UISlider.cpp
    UISlider.h
    UIString.cpp
    UIString.h
    UITabLayout.cpp
    UITabLayout.h
    UIText.cpp
    UIText.h
    UITileLayout.cpp
    UITileLayout.h
    UIUtils.cpp
    UIUtils.h
    UIVerticalLayout.cpp
    UIVerticalLayout.h
    UIWindow.cpp
    UIWindow.h
    WindowImpBase.cpp
    WindowImpBase.h
)

add_library(gtkduilib SHARED ${SRC})
target_include_directories(gtkduilib PUBLIC ${GTK3_INCLUDE_DIRS})
target_link_libraries(gtkduilib ${GTK3_LIBRARIES})

if(WIN32)
    target_link_directories(gtkduilib PUBLIC ${GTK3_LIBRARY_DIRS})
endif()