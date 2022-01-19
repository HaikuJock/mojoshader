To use this in your project:

- Add mojoshader*.c and mojoshader*.h to your project.
- Compile mojoshader*.c
- If you don't have a C99-compliant compiler, like Microsoft Visual Studio,
  you'll need to compile the .c files as C++ to get them to build.
- If you don't have cmake to generate mojoshader_version.h, you can either
  add a blank file with that name, or add MOJOSHADER_NO_VERSION_INCLUDE to
  your preprocessor definitions.

// end of README.txt ...



MonoGame Build Instructions
---------------------------

Windows:

 - From the start menu run "x64 Native Tools Command Prompt for VS 2019"
 - First run `cmake -G "Visual Studio 16 2019" -A Win32 .` to generate projects for 32bit.
 - Open the MojoShader.sln solution and unload the finderrors, test, testoutput, and testparse projects.
 - Select and build the lemon and mojoshader projects under the MinSizeRel config.
 - Copy the 32bit lemon.exe parser generator from the MinSizeRel folder to a safe place.
 - Clean (close the solution and delete all generated files with git) and run `cmake -G "Visual Studio 11 Win64"` to generate 64bit projects.
 cmake -G "Visual Studio 16 2019" -A Win64 -DCMAKE_BUILD_TYPE:STRING="Release" .
 cmake -G "Visual Studio 16 2019" -A Win64 -DCMAKE_CONFIGURATION_TYPES:STRING="MinSizeRel" .
cmake -G "Visual Studio 16 2019" -A Win64 -DCMAKE_C_COMPILER:FILEPATH="C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.28.29333/bin/Hostx64/x64/cl.exe" -DCMAKE_CXX_COMPILER:FILEPATH="C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.28.29333/bin/Hostx64/x64/cl.exe"  -DCMAKE_MAKE_PROGRAM="C:\PROGRAM FILES (X86)\MICROSOFT VISUAL STUDIO\2019\COMMUNITY\COMMON7\IDE\COMMONEXTENSIONS\MICROSOFT\CMAKE\Ninja\ninja.exe" .
 

 - Open the solution and unload the finderrors, test, testoutput, testparse, and lemon projects.
 - Copy the 32bit lemon.exe to the MinSizeRel folder.
 - Select and build the mojoshader project under the MinSizeRel config.
 
 "cmd.exe" /c "%SYSTEMROOT%\System32\chcp.com 65001 >NUL 
 && "C:\PROGRAM FILES (X86)\MICROSOFT VISUAL STUDIO\2019\COMMUNITY\COMMON7\IDE\COMMONEXTENSIONS\MICROSOFT\CMAKE\CMake\bin\cmake.exe"  -G "Visual Studio 11" -DCMAKE_BUILD_TYPE:STRING="Release" -DCMAKE_INSTALL_PREFIX:PATH="C:\Users\jock\src\mojoshader\out\install\x64-Release (default)" -DCMAKE_C_COMPILER:FILEPATH="C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.28.29333/bin/Hostx64/x64/cl.exe" -DCMAKE_CXX_COMPILER:FILEPATH="C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.28.29333/bin/Hostx64/x64/cl.exe"  -DCMAKE_MAKE_PROGRAM="C:\PROGRAM FILES (X86)\MICROSOFT VISUAL STUDIO\2019\COMMUNITY\COMMON7\IDE\COMMONEXTENSIONS\MICROSOFT\CMAKE\Ninja\ninja.exe" "C:\Users\jock\src\mojoshader" 2>&1"
