
ADD_EXECUTABLE(test_raycasting test_raycasting.cpp)
TARGET_LINK_LIBRARIES(test_raycasting optimized octomap${CMAKE_RELEASE_POSTFIX} 
	                                 	 debug octomap${CMAKE_DEBUG_POSTFIX}
	                                 	 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                		 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET test_raycasting PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET test_raycasting PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})	                 

ADD_EXECUTABLE(test_iterators test_iterators.cpp)
TARGET_LINK_LIBRARIES(test_iterators optimized octomap${CMAKE_RELEASE_POSTFIX} 
	                                 	 debug octomap${CMAKE_DEBUG_POSTFIX}
	                                 	 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                		 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET test_iterators PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET test_iterators PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})		                                 	 

ADD_EXECUTABLE(test_io test_io.cpp)
TARGET_LINK_LIBRARIES(test_io optimized octomap${CMAKE_RELEASE_POSTFIX} 
	                                 	 debug octomap${CMAKE_DEBUG_POSTFIX}
	                                 	 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                		 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET test_io PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET test_io PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})	                                 	 

ADD_EXECUTABLE(test_changedkeys test_changedkeys.cpp)
TARGET_LINK_LIBRARIES(test_changedkeys optimized octomap${CMAKE_RELEASE_POSTFIX} 
	                                 	 debug octomap${CMAKE_DEBUG_POSTFIX}
	                                 	 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                		 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET test_changedkeys PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET test_changedkeys PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})		                                 	 

ADD_EXECUTABLE(test_scans test_scans.cpp)
TARGET_LINK_LIBRARIES(test_scans optimized octomap${CMAKE_RELEASE_POSTFIX} 
	                                 	 debug octomap${CMAKE_DEBUG_POSTFIX}
	                                 	 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                		 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET test_scans PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET test_scans PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})			                                 	 

ADD_EXECUTABLE(test_lut test_lut.cpp)
TARGET_LINK_LIBRARIES(test_lut optimized octomap${CMAKE_RELEASE_POSTFIX} 
	                                 	 debug octomap${CMAKE_DEBUG_POSTFIX}
	                                 	 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                		 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET test_lut PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET test_lut PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})		                                 	 

ADD_EXECUTABLE(test_color_tree test_color_tree.cpp)
TARGET_LINK_LIBRARIES(test_color_tree optimized octomap${CMAKE_RELEASE_POSTFIX} 
	                                 	 debug octomap${CMAKE_DEBUG_POSTFIX}
	                                 	 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                		 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET test_color_tree PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET test_color_tree PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})		                                 	 

ADD_EXECUTABLE(color_tree_histogram color_tree_histogram.cpp)
TARGET_LINK_LIBRARIES(color_tree_histogram optimized octomap${CMAKE_RELEASE_POSTFIX} 
	                                 	 debug octomap${CMAKE_DEBUG_POSTFIX}
	                                 	 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                		 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET color_tree_histogram PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET color_tree_histogram PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})	                                 	 

ADD_EXECUTABLE(test_mapcollection test_mapcollection.cpp)
TARGET_LINK_LIBRARIES(test_mapcollection optimized octomap${CMAKE_RELEASE_POSTFIX} 
	                                 	 debug octomap${CMAKE_DEBUG_POSTFIX} 
								  		 optimized octomath${CMAKE_RELEASE_POSTFIX} 
	                              		 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET test_mapcollection PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET test_mapcollection PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})

ADD_EXECUTABLE(test_pruning test_pruning.cpp)
TARGET_LINK_LIBRARIES(test_pruning  optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                 	debug octomap${CMAKE_DEBUG_POSTFIX} 
							  		optimized octomath${CMAKE_RELEASE_POSTFIX} 
                              		debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET test_pruning PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET test_pruning PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})

# CTest tests below

ADD_EXECUTABLE(unit_tests unit_tests.cpp)
TARGET_LINK_LIBRARIES(unit_tests octomap)
SET_PROPERTY(TARGET unit_tests PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET unit_tests PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})

ADD_TEST (NAME MathVector         COMMAND unit_tests MathVector     )
ADD_TEST (NAME MathPose           COMMAND unit_tests MathPose       )
ADD_TEST (NAME InsertRay          COMMAND unit_tests InsertRay      )
ADD_TEST (NAME InsertScan         COMMAND unit_tests InsertScan     )
ADD_TEST (NAME ReadGraph          COMMAND unit_tests ReadGraph      )
ADD_TEST (NAME StampedTree        COMMAND unit_tests StampedTree    )
ADD_TEST (NAME OcTreeKey          COMMAND unit_tests OcTreeKey      )
ADD_TEST (NAME test_raycasting    COMMAND test_raycasting)
ADD_TEST (NAME test_io            COMMAND test_io ${PROJECT_SOURCE_DIR}/share/data/geb079.bt)
ADD_TEST (NAME test_pruning       COMMAND test_pruning )
ADD_TEST (NAME test_iterators     COMMAND test_iterators ${PROJECT_SOURCE_DIR}/share/data/geb079.bt)
ADD_TEST (NAME test_mapcollection COMMAND test_mapcollection ${PROJECT_SOURCE_DIR}/share/data/mapcoll.txt)
ADD_TEST (NAME test_color_tree    COMMAND test_color_tree)
