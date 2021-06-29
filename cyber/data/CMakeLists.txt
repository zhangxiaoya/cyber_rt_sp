set(TARGET_NAME cyber_data)

file(GLOB H_FILES *.h)
file(GLOB FUSION_H_FILES fusion/*.h)
file(GLOB HPP_FILES *.hpp)
set(${TARGET_NAME}_hdrs ${H_FILES} ${HPP_FILES})

install(FILES ${${TARGET_NAME}_hdrs} DESTINATION include/cyber/data)
install(FILES ${FUSION_H_FILES} DESTINATION include/cyber/data/fusion)
