add_executable(svg_exec
                    main.cpp)

target_link_libraries(svg_exec
                        PRIVATE
                            svg_lib)