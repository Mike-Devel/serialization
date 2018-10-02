# Copyright 2018 Mike Dev
# Distributed under the Boost Software License, Version 1.0.
# See accompanying file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt

cmake_minimum_required(VERSION 3.5)
project(BoostSerialization LANGUAGES CXX)

file(GLOB BOOST_SERIALIZATION_SRC ./src/*.cpp)

add_library(boost_serialization ${BOOST_SERIALIZATION_SRC})
add_library(Boost::serialization ALIAS boost_serialization)

target_include_directories(boost_serialization PUBLIC include)

target_link_libraries(boost_serialization
    PUBLIC
        Boost::array
        Boost::assert
        Boost::config
        Boost::core
        Boost::detail
        Boost::integer
        Boost::io
        Boost::iterator
        Boost::move
        Boost::mpl
        Boost::optional
        Boost::predef
        Boost::preprocessor
        Boost::smart_ptr
        Boost::spirit
        Boost::static_assert
        Boost::type_traits
        Boost::unordered
        Boost::utility
        Boost::variant
)
