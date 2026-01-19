# 🛠️ Setup & Installation Instructions

This project is built on **Unreal Engine 5 (C++)**. The repository follows "Clean Architecture" standards: intermediate files, binaries, and caches are excluded to maintain a lightweight history. Please follow the instructions below to build the project locally.

## 📋 Prerequisites

Before starting, ensure you have the following installed:

1.  **Unreal Engine 5.x** (Match the version specified in the `.uproject` file).
2.  **Visual Studio 2022**.
    * **Workload:** *"Game development with C++"*.
    * **Required Components:** *MSVC v143*, *Windows 10/11 SDK*, *IDE support for Unreal Engine*.
3.  **Git** with **LFS** (Large File Storage) support.

## 🚀 Installation Guide

### 1. Clone the Repository
Since this project uses plugins (e.g., PaperZD) as git submodules, the `--recursive` flag is required.
Open your terminal (Git Bash / PowerShell)
```bash
git clone --recursive https://github.com/ConstantineManychev/HorrorGameUE5.git
```
If you cloned without the recursive flag, run this inside the project folder:
```bash
git submodule update --init --recursive
```

###2. Generate Project Files
The Visual Studio solution file (.sln) is not tracked in the repository. It must be generated for your specific machine.

Navigate to the project root folder.

Right-click on YourProjectName.uproject.

Select Generate Visual Studio project files.

Wait for the YourProjectName.sln file to appear.

###3. Compile (Build)
Open YourProjectName.sln in Visual Studio 2022 (or Rider).

Set the build configuration to:

Solution Configuration: Development Editor

Solution Platform: Win64

Press Build -> Build Solution (or Ctrl+Shift+B).

Note: The first build may take some time as it compiles the C++ modules and plugins.

###4. Run
Once the build is successful, you can launch the project:

Via IDE: Press F5 to Start Debugging.

Via File: Double-click YourProjectName.uproject.

#⚠️ Troubleshooting
Issue: "Missing Modules" or "PaperZD" error upon launch.

Solution: You skipped Step 3. C++ plugins require compilation. You must build the project via Visual Studio before opening the .uproject file.

Issue: "Could not find definition for module..." error during file generation.

Solution: Ensure the Plugins/PaperZD folder is not empty. If it is, run git submodule update --init --recursive.

Issue: Long shader compilation on first launch.

Solution: This is expected behavior. The DerivedDataCache is not version-controlled; the engine is rebuilding shaders for your specific hardware.
