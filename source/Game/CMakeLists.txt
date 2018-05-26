# Target
if(WIN32)
	add_executable(Game WIN32 "main.cpp")
else()
	add_executable(Game "main.cpp")
endif()
	
# Working directory
set_target_properties(Game PROPERTIES VS_DEBUGGER_WORKING_DIRECTORY "$(OutDir)")		
	
# Libraries
## Local libs
target_link_libraries(Game Common)

# Plugin dependencies
add_engine_dependencies(Game)
add_dependencies(Game bsfFBXImporter bsfFontImporter bsfFreeImgImporter)

# IDE specific
set_property(TARGET Game PROPERTY FOLDER Demo)