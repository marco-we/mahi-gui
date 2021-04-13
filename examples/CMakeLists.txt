macro(mahi_gui_example target)
    # create executable
    add_executable(${target} "ex_${target}.cpp" my_icon.rc)
    # set dependencies
    target_link_libraries(${target} mahi::gui)
    # add install rule
    install(TARGETS ${target}
      RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
    )
    set_target_properties(${target} PROPERTIES FOLDER "Examples")
    set_target_properties(${target} PROPERTIES DEBUG_POSTFIX -d)
endmacro(mahi_gui_example)

mahi_gui_example(imgui_demo)
mahi_gui_example(implot_demo)
mahi_gui_example(plots_benchmark)
mahi_gui_example(dpi)
mahi_gui_example(likert)
mahi_gui_example(events)
mahi_gui_example(hidden)
mahi_gui_example(log_window)
mahi_gui_example(opengl)
mahi_gui_example(gears)
mahi_gui_example(raw_glfw)

if (MAHI_GUI_NATIVE_DIAGS)
    mahi_gui_example(files)
endif()
