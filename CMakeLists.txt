#
#  Copyright CNRS
#
#  Author: Olivier Stasse
#
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

INCLUDE(cmake/base.cmake)
INCLUDE(cmake/cpack.cmake)

SET(PROJECT_NAME gerard-bauzil)
SET(PROJECT_DESCRIPTION "Gerard Bauzil data files")
SET(PROJECT_URL "")

SETUP_PROJECT()
ADD_SUBDIRECTORY(data)

SETUP_PROJECT_FINALIZE()
SETUP_PROJECT_CPACK()