# Copyright 2024 The Mako Authors
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

add_subdirectory(nn)
add_subdirectory(utils)

add_executable(${CMAKE_PROJECT_NAME} main.cc)
target_include_directories(
  ${CMAKE_PROJECT_NAME}
  PUBLIC
  ${TORCH_INCLUDE_DIRS}
  ${CMAKE_SOURCE_DIR})
target_link_libraries(
  ${CMAKE_PROJECT_NAME}
  ${TORCH_LIBRARIES}
  absl::log
  absl::strings
  ${Boost_CONTEXT_LIBRARY}
  mako::nn
  mako::utils)
