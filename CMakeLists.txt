CMAKE_MINIMUM_REQUIRED( VERSION 2.6 )

FIND_PACKAGE( ITK REQUIRED )

IF( ITK_FOUND )
  INCLUDE( ${ITK_USE_FILE} )
ENDIF( ITK_FOUND )

SET( APPS
  QuadricDecimation
  Decimation
  Smoothing
)

FOREACH( var ${APPS} )
  ADD_EXECUTABLE( ${var} ${var}.cxx )
  TARGET_LINK_LIBRARIES( ${var} ITKIO ITKQuadEdgeMesh )
ENDFOREACH( var ${APPS} )

