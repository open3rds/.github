## Python

pip

```shell
pip install git+https://github.com/open3rds/${python_module}.git
```
requirements.txt
```shell
git+git://github.com/open3rds/${python_module}.git@0.1#egg=${python_module}
```

## C++

cmake

```python
# CMake Version > v3.11
FetchContent_Declare(${lib_name}
        GIT_REPOSITORY https://github.com/open3rds/${python_module}.git
        GIT_TAG ${version})
FetchContent_MakeAvailable(${lib_name})
target_link_libraries(${app_name} PRIVATE ${lib_name}::${cmake_project_name})
```
xmake

```lua
add_repositories("open3rds git@github.com:open3rds/xmake-repo.git main")
-- add_repositories("open3rds git@github.com:open3rds/xmake-repo.git experiment")
add_requires("open3rds::${lib_name}  1.0.x", {alias = "${lib_name}"})
target("test")
    set_kind("binary")
    add_files("src/*.cpp")
    add_packages("open3rds::${lib_name}")
```

## Go

use github

## Java

N/A
