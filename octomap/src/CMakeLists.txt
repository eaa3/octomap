
SET (octomap_SRCS
  AbstractOcTree.cpp
  AbstractOccupancyOcTree.cpp
  Pointcloud.cpp
  ScanGraph.cpp
  CountingOcTree.cpp
  OcTree.cpp
  OcTreeNode.cpp
  OcTreeStamped.cpp
  OcTreeLUT.cpp
  ColorOcTree.cpp
  )

# dynamic and static libs, see CMake FAQ:
ADD_LIBRARY( octomap SHARED ${octomap_SRCS})
set_target_properties( octomap PROPERTIES
  VERSION ${OCTOMAP_VERSION}
  SOVERSION ${OCTOMAP_SOVERSION}
)
SET_PROPERTY(TARGET octomap PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET octomap PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})

ADD_LIBRARY( octomap-static STATIC ${octomap_SRCS})
SET_TARGET_PROPERTIES(octomap-static PROPERTIES OUTPUT_NAME "octomap") 
SET_PROPERTY(TARGET octomap-static PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET octomap-static PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})


TARGET_LINK_LIBRARIES(octomap optimized octomath${CMAKE_RELEASE_POSTFIX} 
                              debug octomath${CMAKE_DEBUG_POSTFIX})

ADD_SUBDIRECTORY( testing )

ADD_EXECUTABLE(graph2tree graph2tree.cpp)
TARGET_LINK_LIBRARIES(graph2tree optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                 debug octomap${CMAKE_DEBUG_POSTFIX}
                                 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET graph2tree PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET graph2tree PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})                                 

ADD_EXECUTABLE(log2graph log2graph.cpp)
TARGET_LINK_LIBRARIES(log2graph optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                 debug octomap${CMAKE_DEBUG_POSTFIX}
                                 optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                 debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET log2graph PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET log2graph PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})    

ADD_EXECUTABLE(binvox2bt binvox2bt.cpp)
TARGET_LINK_LIBRARIES(binvox2bt optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                debug octomap${CMAKE_DEBUG_POSTFIX}
                                optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET binvox2bt PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET binvox2bt PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 

ADD_EXECUTABLE(bt2vrml bt2vrml.cpp)
TARGET_LINK_LIBRARIES(bt2vrml optimized octomap${CMAKE_RELEASE_POSTFIX} 
                              debug octomap${CMAKE_DEBUG_POSTFIX}
                              optimized octomath${CMAKE_RELEASE_POSTFIX} 
                              debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET bt2vrml PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET bt2vrml PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 

ADD_EXECUTABLE(edit_octree edit_octree.cpp)
TARGET_LINK_LIBRARIES(edit_octree optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                  debug octomap${CMAKE_DEBUG_POSTFIX}
                                  optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                  debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET edit_octree PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET edit_octree PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 

ADD_EXECUTABLE(convert_octree convert_octree.cpp)
TARGET_LINK_LIBRARIES(convert_octree optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                     debug octomap${CMAKE_DEBUG_POSTFIX}
                                     optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                     debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET convert_octree PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET convert_octree PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 

ADD_EXECUTABLE(eval_octree_accuracy eval_octree_accuracy.cpp)
TARGET_LINK_LIBRARIES(eval_octree_accuracy optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                           debug octomap${CMAKE_DEBUG_POSTFIX}
                                           optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                           debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET eval_octree_accuracy PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET eval_octree_accuracy PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 

ADD_EXECUTABLE(compare_octrees compare_octrees.cpp)
TARGET_LINK_LIBRARIES(compare_octrees optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                      debug octomap${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET compare_octrees PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET compare_octrees PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 

ADD_EXECUTABLE(simple_example simple_example.cpp)
TARGET_LINK_LIBRARIES(simple_example optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                     debug octomap${CMAKE_DEBUG_POSTFIX}
                                     optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                     debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET simple_example PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET simple_example PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 

ADD_EXECUTABLE(normals_example normals_example.cpp)
TARGET_LINK_LIBRARIES(normals_example optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                      debug octomap${CMAKE_DEBUG_POSTFIX}
                                      optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                      debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET normals_example PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET normals_example PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 

ADD_EXECUTABLE(intersection_example intersection_example.cpp)
TARGET_LINK_LIBRARIES(intersection_example optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                           debug octomap${CMAKE_DEBUG_POSTFIX}
                                           optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                           debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET intersection_example PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET intersection_example PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 

ADD_EXECUTABLE(octree2pointcloud octree2pointcloud.cpp)
TARGET_LINK_LIBRARIES(octree2pointcloud optimized octomap${CMAKE_RELEASE_POSTFIX} 
                                        debug octomap${CMAKE_DEBUG_POSTFIX}
                                        optimized octomath${CMAKE_RELEASE_POSTFIX} 
                                        debug octomath${CMAKE_DEBUG_POSTFIX})
SET_PROPERTY(TARGET octree2pointcloud PROPERTY RELEASE_POSTFIX ${CMAKE_RELEASE_POSTFIX})
SET_PROPERTY(TARGET octree2pointcloud PROPERTY DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX}) 


# installation:
# store all header files to install:
# file(GLOB octomap_impl_HDRS *.h *.hxx *.hpp)
# install(FILES ${octomap_impl_HDRS} DESTINATION include/octomap)

install(TARGETS 
	octomap
	octomap-static 
	graph2tree
	log2graph
	binvox2bt
	bt2vrml
	edit_octree
	convert_octree
	eval_octree_accuracy
	compare_octrees
	${INSTALL_TARGETS_DEFAULT_ARGS}
)

