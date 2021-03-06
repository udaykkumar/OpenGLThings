
# Minimum CMake
cmake_minimum_required(VERSION 2.8,9)
project( play_graphics )
enable_testing()


add_executable( hellow_world         		hellow_world.cpp )
add_executable( glfw_hello_world   			glfw_hello_world.cpp )
add_executable( glfw_hello_shapes_triangle 			glfw_hello_shapes_triangle.cpp shader.cpp )
add_executable( glfw_hello_moving_shapes_triangle	glfw_hello_moving_shapes_triangle.cpp shader.cpp )
add_executable( glfw_hello_metrices 		glfw_hello_metrices.cpp shader.cpp )
add_executable( glfw_hello_coloured_cube 	glfw_hello_coloured_cube.cpp shader.cpp )



if(APPLE)
	target_link_libraries(hellow_world ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-framework OpenGL" )
	target_link_libraries(glfw_hello_world ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-framework OpenGL" )
	target_link_libraries(glfw_hello_shapes_triangle ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-framework OpenGL" )
	target_link_libraries(glfw_hello_moving_shapes_triangle ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-framework OpenGL" )
	target_link_libraries(glfw_hello_metrices ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-framework OpenGL" )
	target_link_libraries(glfw_hello_coloured_cube ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-framework OpenGL" )
	
else()
	target_link_libraries(hellow_world ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-lGL -lGLU -lglut" )
	target_link_libraries(glfw_hello_world ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-lGL -lGLU -lglut" )
	target_link_libraries(glfw_hello_shapes_triangle ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-lGL -lGLU -lglut" )
	target_link_libraries(glfw_hello_moving_shapes_triangle ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-lGL -lGLU -lglut" )
	target_link_libraries(glfw_hello_metrices ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-lGL -lGLU -lglut" )
	target_link_libraries(glfw_hello_coloured_cube ${GLFW3_LIBRARY} ${GLEW_LIBRARY} "-lGL -lGLU -lglut" )
	
endif()

configure_file(SimpleVertexShader.vertexshader SimpleVertexShader.vertexshader COPYONLY)
configure_file(SimpleFragmentShader.fragmentshader SimpleFragmentShader.fragmentshader COPYONLY)

configure_file(SingleColor.fragmentshader SingleColor.fragmentshader COPYONLY)
configure_file(SimpleTransform.vertexshader SimpleTransform.vertexshader COPYONLY)

configure_file(ColorFragmentShader.fragmentshader ColorFragmentShader.fragmentshader COPYONLY )
configure_file(TransformVertexShader.vertexshader TransformVertexShader.vertexshader COPYONLY )


