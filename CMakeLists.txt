cmake_minimum_required(VERSION 3.15) # Проверка версии CMake.
									 # Если версия установленой программы
									 # старее указаной, произайдёт аварийный выход.

set(PROJECT_NAME WORLD OF GALLOWS)				 # имя проекта		 
project("${PROJECT_NAME}")


set(CMAKE_CXX_STANDARD 17)			 # устанавливаем 17 стандарт языка
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)


add_definitions(-DSFML_STATIC)		 # дефайны

include_directories("ext/SFML/include/")	# добавляем директории
link_directories("ext/SFML/lib/")	

add_executable("${PROJECT_NAME}" main.cpp
                                 Expection.hpp
                                 Game.cpp
			      	 Game.hpp
				 Random.ccp
                                 Random.hpp
                                 Snake.cpp
		                 Snake.hpp
)
											
target_link_libraries("${PROJECT_NAME}" sfml-graphics-s-d
						  sfml-window-s-d
						  sfml-system-s-d
						  opengl32
						  freetype
						  winmm
						  gdi32
						  sfml-audio-s-d
						  openal32
						  flac
						  vorbisenc
						  vorbisfile
						  vorbis
						  ogg)
file(COPY "data/apple.png" DESTINATION "/data/")
file(COPY "data/body.png" DESTINATION "/data/")
file(COPY "data/border.png" DESTINATION "/data/")
file(COPY "data/cell.png" DESTINATION "/data/")
file(COPY "data/font.ttf" DESTINATION "/data/")
file(COPY "data/game_over.png" DESTINATION "/data/")
file(COPY "assets/head.png" DESTINATION "/data/")