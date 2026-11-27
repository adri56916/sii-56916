CMAKE_MINIMUM_REQUIRED(VERSION 3.10)
PROJECT (TENIS)

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/include)

SET(COMMON_SRCS
    src/Esfera.cpp
    src/Plano.cpp
    src/Raqueta.cpp
    src/Vector2D.cpp
)

add_executable(logger src/logger.cpp)

add_executable(bot src/bot.cpp)

add_executable(servidor src/servidor.cpp src/MundoServidor.cpp ${COMMON_SRCS})
TARGET_LINK_LIBRARIES(servidor glut GL GLU pthread)

add_executable(cliente src/cliente.cpp src/MundoCliente.cpp ${COMMON_SRCS})
TARGET_LINK_LIBRARIES(cliente glut GL GLU)
