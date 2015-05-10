Windows
=======

From run (Control-R):

    eventvwr        # Event Viewer
    diskmgmt.msc
    services.msc
    
Usual stuff:

    explorer
    cmd
    powershell

Visual Studio

    msbuild someproj.csproj /v:diag
    
Cmd

    findstr /spin FooText *        & REM Grep a string
    dir /b /s *FooFile*            & REM Search for filename
    tree /f                        & REM tree cmd showing filenames in each directory
    tree /f .\SomeDirectory
    start .                        & REM Launches explorer.exe for current directory
