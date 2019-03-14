cmake_minimum_required(VERSION 3.2)

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.23.131.tar.gz"
    SHA1 "0512ea6392065c8ece808296fddd7d8664d30920"
)

project(foo)

# Just a small package to initialize Hunter
hunter_add_package(md5)

include(hunter_check_toolchain_definition)
hunter_check_toolchain_definition(
    NAME __amd64__
    DEFINED x64_architecture
)

message("x64_architecture: ${x64_architecture}")
