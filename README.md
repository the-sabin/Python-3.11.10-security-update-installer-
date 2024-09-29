Source code was downloaded from:
https://www.python.org/ftp/python/3.11.10/Python-3.11.10.tgz


Pre-requisites:
1.Installed Visual Studio Code 2022 Community:
    a. From Workloads: select **Python development**
    b. From Installation details --> under Optional section: select Python native development
    c. From Individual components: make sure this compoenent is selected --> **MSVC v143 - VS 2022 C++ x64/x86 build tools (Latest)**
    d. **Important** --> Even though its compiled for x64, the installer creation process would fail without this component so you may need to select it --> **MSVC v143 - VS 2022 C++ ARM64/ARM64EC build tools (Latest)**
      Found this dicussion here which was helpul to figure this out: https://github.com/python/cpython/issues/106765
2. Windows 11 --> Start --> find **Turn Windows features on or off** and launch this dialog --> expand the **.NET Framework 3.5 (include .NET 2.0 and 3.0)** and select both options in order to have the parent checkbox checked--> click OK on this dialog.

Steps followed:
1. Set up pre-requisites.
2. Extract Python-3.11.10.tgz archive.
3. Launch a command prompt inside the Python folder that was extracted.
4. CD to PCbuild\ and execute get_externals.bat
5. Execute: build.bat -p x64 -c Release
6. Execute: build.bat -p x64 --pgo
7. [Optional]: navigate to PCbuild\amd64 and test the python.exe
   
  Start Building the Installer
8. CD to Tools\msi folder.
9. Execute the get_Externals.bat
10. Build the installer: buildrelease.bat -x64 --skip-nuget --skip-zip
11. If things went well you should have a **python-3.11.10-amd64.exe** inside the PCbuild\amd64\en-us folder.
