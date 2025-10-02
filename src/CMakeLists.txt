cmake_minimum_required(VERSION 3.20)

project(EnemyNations LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_MFC_FLAG 2)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../windward ${CMAKE_BINARY_DIR}/windward)

set(GAME_SOURCES
    Ai.cpp
    area.cpp
    bmbutton.cpp
    bridge.cpp
    caicopy.cpp
    caidata.cpp
    caigmgr.cpp
    caigoal.cpp
    caihex.cpp
    caiinit.cpp
    caimap.cpp
    caimaput.cpp
    caimgr.cpp
    caimsg.cpp
    caiopfor.cpp
    cairoute.cpp
    caisavld.cpp
    caistart.cpp
    caitask.cpp
    caitmgr.cpp
    caiunit.cpp
    CdLoc.cpp
    chat.cpp
    chatbar.cpp
    chproute.cpp
    cpathmap.cpp
    cpathmgr.cpp
    creatmul.cpp
    creatsin.cpp
    credits.cpp
    cutscene.cpp
    dlgflic.cpp
    DlgMsg.cpp
    DlgReg.cpp
    Dxfer.cpp
    event.cpp
    icons.cpp
    ipcchat.cpp
    ipccomm.cpp
    ipcmsg.cpp
    ipcplay.cpp
    ipcread.cpp
    ipcsend.cpp
    join.cpp
    lastplnt.cpp
    Lastplnt.rc
    license.cpp
    loadtruk.cpp
    main.cpp
    Mainloop.cpp
    minerals.cpp
    movie.cpp
    netapi.cpp
    netcmd.cpp
    new_game.cpp
    new_unit.cpp
    newworld.cpp
    options.cpp
    pickrace.cpp
    player.cpp
    PlyrList.cpp
    projbase.cpp
    racedata.cpp
    relation.cpp
    research.cpp
    scenario.cpp
    sprite.cpp
    sprtinit.cpp
    stdafx.cpp
    terrain.cpp
    toolbar.cpp
    tstsnds.cpp
    unit.cpp
    unit_wnd.cpp
    vehicle.cpp
    Vehmove.cpp
    vehoppo.cpp
    VPXFER.CPP
    world.cpp
    wrldinit.cpp
    RES/VERSION.RC
)

add_executable(EnemyNations WIN32 ${GAME_SOURCES})

if(MSVC)
    target_compile_options(EnemyNations PRIVATE /utf-8)
endif()

target_precompile_headers(EnemyNations PRIVATE stdafx.h)

target_include_directories(EnemyNations
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}
        ${CMAKE_CURRENT_SOURCE_DIR}/../windward/include
)

target_compile_definitions(EnemyNations
    PRIVATE
        WIN32
        _WINDOWS
        _MBCS
        _AFXDLL
        VDMPLAY_STATIC
)

target_link_libraries(EnemyNations
    PRIVATE
        windward
        shlwapi
        vfw32
        winmm
        version
        comctl32
        comdlg32
        user32
        gdi32
)

