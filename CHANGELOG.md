# Changelog

## [Unreleased]
### Added
  - Add support to use different project types (EWARM, STM32CubeIDE, etc.).
  - Add ability to introduce generated changes from the main.c file into the main.cpp file.
  - Add a separate file for config options, like compiler flags.
  - Add support for unit testing using Google Test and Google Mock.
  - Add support for windows with xpm install.
  - Add dual bank support
  - Added debug info for chips not working.
  - Switch to xpm for all platforms to install missing packages.
  - Include dfu programming.
  - 
## [2.2.4] - 2020-09-16
### Fixed
 - Issue #36: rm command is not found on windows. Used suggested fix by bw1faeh0
  
## [2.2.3] - 2020-09-08
### Fixed
 - Fixed issue where the makefile did not respond well to relative paths for the gcc compiler.

## [2.2.2] - 2020-09-07
### Fixed
 - Issue #25: Added absolute compiler path to c_cpp_properties.json

## [2.2.1] - 2020-09-07
### Added
 - Issue #11 & Issue #33 : Add support for different programmers.
  
## [2.2.0] - 2020-09-04
### Fixed
 - Issue #32: Switched to g++ linker when linking C++ project.
 - Issue with clean build on Windows where the remove command did not work
 - Issue #25: Buggy IntelliSense, removed compiler in the c_cpp_properties.json, intellisense works fine without it.
 - Issue #32: Did not use g++ linker when compiling library files. It now uses g++ linker when compiling C++

### Added
- Added support for new STM32 Devices in OpenOCD 0.10.0-20200310 (merge request #18 by seancsi)
- Issue #22: Added support for the advanced project structure.
- Support for libraries and automatic inclusion in libs directory (with support from seancsi)
- Merge #31: Added github actions for testing (thanks to klaygomes)
- Added testing to a lot of files to speed up feature implementation and stability.

## [2.1.5] - 2020-03-13
### Fixed
 - Issue #15: Fixed overwrite off c_cpp_properties and retained added folders.
 - Make exits before completion. This makes debugger not act on the new file.
 - Fixed issue where deeper inclusions in Src or Inc did not have forward slash in windows

### Added
- Issue #9: Add an .stmignore file for ignoring globs.
- Automatically ignore files in test and example in the lib folder (using default .stmignore file).

## [2.0.5] - 2019-11-25
### Fixed
 - Fixed issue where the launch, c_cpp_properties and task files would not be created.

## [2.0.4] - 2019-11-02
### Fixed
 - Fixed issue with clean build on linux (merged fix from Bonnee)
 - Fixed autogenerated debug configuration fail
 - Fixed Build terminal won't open again

## [2.0.3] - 2019-10-28
### Fixed
 - Fixed an issue where the extension would not startup on flash

## [2.0.2] - 2019-10-20
### Fixed
 - Fix addition of main.c on windows machines during a .cpp project
 - Fix compilation issues when using STM32L031

### Changed
 - Switch from regular fs to VSCode's workspace fs

## [2.0.1] - 2019-10-15
### Fixed
 - Fixed issue which could potentially crash the requirements check
 - Fixed bug for not writing launch and json files when the .vscode folder was not present.
 - Fixed issue with not showing pop-up for tools on Windows.
 - Fixed path seperators are different on windows, copied style of STM32Cube generated makefile
 - Fixed issue where sub directories of library files are not added on Windows, because of path seperators

## [2.0.0] - 2019-10-07
### Added
 - Added support for task compilation using the build in extension commands.
 - Added support for problem matching while compiling for STM.
 - Added download link in the tool missing pop-up.
 - Added brew install on OSX for the tool missing pop-up. 
 - Added apt-get for linux for the tool missing pop-up.
 - Added add path for the tool missing pop-up.
 - Added full support to add the tool path in the extension settings.
 - Added support to auto configure cortex-debug settings.
 - Added internal tests for the extension.
 - Added auto intellisense management for STM32 projects.

### Changed
- Stricter adherence to Src, Inc and Lib folders.
- Libraries are added through the definition in the makefile for faster compilation and to not include superfluous .c files
- Packaged the app.

### Removed
 - Removed dependency on the external STM32 for VSCode CLI.
 - Removed dependency on the external ST-Flash tool.

## [1.8.6] - 2017-07-30
### Added

### Changed

### Fixed
 - Because of packaging things went awry. Fixed through not using the package

## [1.8.1] - 2017-07-30
### Added

### Changed

### Fixed
 - Packaging needed entry point in package.json to be changed.

## [1.8.0] - 2017-07-23
### Added
 - Added support for Cortex-Debug configuration file for debugging.
 - Added support for main.cpp file in conjunction with a main.c file, it will auto compile for the main.cpp [EXPERIMENTAL]

### Changed
 - Stopped overwriting makefile and created stm32make file instead.
 - Stopped checking for requirements in the build CLI.

### Fixed
 - Stopped adding unnecessary .h files in includes.
 - Stopped unnecessary remake of makefile.
 - Fixed NPM package vulnerabilities.
