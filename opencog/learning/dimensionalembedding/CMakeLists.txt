ADD_LIBRARY (dimensionalembedding SHARED
	DimEmbedModule
	CoverTreePoint
)

ADD_DEPENDENCIES(dimensionalembedding opencog_atom_types)

INCLUDE_DIRECTORIES (
	${CMAKE_BINARY_DIR}
	${ODBC_INCLUDE_DIRS}
)

IF (CYGWIN)
	INSTALL (TARGETS dimensionalembedding
		DESTINATION "lib${LIB_DIR_SUFFIX}/opencog"
	)
ELSE (CYGWIN)
	INSTALL (TARGETS dimensionalembedding
		LIBRARY DESTINATION "lib${LIB_DIR_SUFFIX}/opencog"
	)
ENDIF (CYGWIN)

TARGET_LINK_LIBRARIES (dimensionalembedding
	cogutil 
)
