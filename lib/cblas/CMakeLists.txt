

# list sources files
FILE(GLOB LIBRARY_FILES_C "./*.c")
FILE(GLOB LIBRARY_FILES_H "./*.h")

SET_SOURCE_FILES_PROPERTIES(${LIBRARY_FILES_C}
  PROPERTIES
  COMPILE_FLAGS "-DADD_")
SET_SOURCE_FILES_PROPERTIES(${LIBRARY_FILES_H}
  PROPERTIES
  COMPILE_FLAGS "-DADD_")

ADD_LIBRARY(cblas
${LIBRARY_FILES_C}
${LIBRARY_FILES_H}
)

INSTALL(TARGETS cblas DESTINATION lib)
