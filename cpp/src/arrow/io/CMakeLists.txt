# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.

# ----------------------------------------------------------------------
# arrow_io : Arrow IO interfaces

add_arrow_test(buffered-test PREFIX "arrow-io")
add_arrow_test(compressed-test PREFIX "arrow-io")
add_arrow_test(file-test PREFIX "arrow-io")

if(ARROW_HDFS AND NOT ARROW_BOOST_HEADER_ONLY)
  add_arrow_test(hdfs-test NO_VALGRIND PREFIX "arrow-io")
endif()

add_arrow_test(memory-test PREFIX "arrow-io")
add_arrow_test(readahead-test PREFIX "arrow-io")

add_arrow_benchmark(file-benchmark PREFIX "arrow-io")
add_arrow_benchmark(memory-benchmark PREFIX "arrow-io")

# Headers: top level
arrow_install_all_headers("arrow/io")
