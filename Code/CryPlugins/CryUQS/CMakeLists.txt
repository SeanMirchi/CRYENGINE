if(OPTION_ENGINE)
	option(PLUGIN_CRYUQS "Enable CryUQS" ON)
else()
	option(PLUGIN_CRYUQS "Enable CryUQS" OFF)
endif()

if (NOT PLUGIN_CRYUQS)
	return()
endif()

add_subdirectory("Client")
add_subdirectory("Core")
add_subdirectory("DataSource_XML")
add_subdirectory("Interfaces")
add_subdirectory("Shared")
add_subdirectory("StdLib")

if (OPTION_SANDBOX AND WIN64)
	add_subdirectory(EditorPlugin)
	add_subdirectory(EditorPlugin_HistoryInspector)
endif()
