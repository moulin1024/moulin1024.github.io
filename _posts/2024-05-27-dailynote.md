## Daily note 20240527

### Libomp error 
When I remove the LD_LIBRARY path

`export LD_LIBRARY_PATH=${CRAY_ROCM_DIR}/llvm/lib:$LD_LIBRARY_PATH`

in `./confix/bash_tools/rocm_setup.sh`, this error occur:

`libomp.so: cannot open shared object file: No such file or directory`

It cannot find `libomp` without this line.

### Add macros

I thought the solver can read all the environmental variable as macro flags. It turns out that it was not the case. In the folder, there is a file `parallax_csr_solver_config.hxx.in`. You have to add `#cmakedefine PARALLAX_CSR_SOLVER_ENABLE_HIP` to define it.

What is this hxx.in thing? Explained by ChatGPT:

The file extensions `.cxx` and `.cxx.in` typically indicate different purposes and usages in a C++ development environment, especially when using build systems like CMake.

- **Purpose**: The `.cxx` file is a standard C++ source code file, similar to `.cpp`, `.cc`, and `.C`. It contains the actual C++ code that gets compiled into object files and eventually linked into an executable or a library.
- **Usage**: This file is directly written by the developer and contains the implementation of the program logic, functions, classes, etc.

```cxx
// example.cxx
#include <iostream>

int main() {
    std::cout << "Hello, world!" << std::endl;
    return 0;
}
```

- **Purpose**: The `.cxx.in` file is a template or input file used in conjunction with a configuration or build system (commonly CMake). It contains placeholders or variables that are replaced with actual values during the configuration process to generate a `.cxx` file.
- **Usage**: This file is not directly compiled. Instead, it is processed by tools like CMake, which replaces the placeholders with actual values (e.g., configuration options, paths, version numbers) to generate a final `.cxx` file that is then compiled.

1. **CMakeLists.txt Configuration**: In the CMake configuration file (`CMakeLists.txt`), you specify how to process the `.in` file.

2. **Processing the .in File**: When you run CMake, it processes `example.cxx.in`, replacing placeholders like `@PROJECT_VERSION@` and `@CMAKE_INSTALL_PREFIX@` with their corresponding values (`1.0.0` and `/usr/local`, respectively).


### Summary

- **`.cxx` File**: A regular C++ source file that is directly written and compiled.
- **`.cxx.in` File**: A template file used by build systems like CMake to generate a `.cxx` file by replacing placeholders with actual values during the configuration process.

The use of `.cxx.in` files allows for greater flexibility and configurability in C++ projects, making it easier to manage different build configurations and environments.