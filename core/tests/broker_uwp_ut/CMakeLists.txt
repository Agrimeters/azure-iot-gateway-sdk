#Copyright (c) Microsoft. All rights reserved.
#Licensed under the MIT license. See LICENSE file in the project root for full license information.

cmake_minimum_required(VERSION 2.8.11)

add_definitions(-DUWP_BINDING)

compileAsC99()
set(theseTestsName broker_uwp_ut)
set(${theseTestsName}_cpp_files
${theseTestsName}.cpp
)

set_source_files_properties(../../src/broadcast_broker.c PROPERTIES LANGUAGE CXX) 
set(${theseTestsName}_c_files
	../../src/broadcast_broker.c
)

set(${theseTestsName}_h_files
)

include_directories(${GW_INC})

build_test_artifacts(${theseTestsName} ON)
