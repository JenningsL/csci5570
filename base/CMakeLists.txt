include_directories(${PROJECT_SOURCE_DIR} ${HUSKY_EXTERNAL_INCLUDE})

file(GLOB base-src-files
  serialization.cpp)

add_library(base-objs OBJECT ${base-src-files} ../worker/app_blocker.hpp ../worker/worker_helper_thread.cpp ../worker/worker_thread.hpp ../lib/svm_loader.hpp ../lib/svm_sample.hpp)
set_property(TARGET base-objs PROPERTY CXX_STANDARD 11)
add_dependencies(base-objs ${external_project_dependencies})
