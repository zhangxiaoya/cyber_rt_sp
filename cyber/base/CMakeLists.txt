cmake_minimum_required(VERSION 3.12)

# install header files
file(GLOB HEADERS *.h)
install(FILES ${HEADERS} DESTINATION ${CYBER_INSTALL_INCLUDE_DIR}/cyber/base/)
