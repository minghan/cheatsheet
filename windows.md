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
    
Cmd ([Microsoft TechNet Reference](https://technet.microsoft.com/en-us/library/cc754340.aspx))
----------------------------------------------------------------------------------------------

Common Operations

    findstr /spin FooText *        & REM Grep a string
    dir /b /s *FooFile*            & REM Search for filename
    tree /f                        & REM tree cmd showing filenames in each directory
    tree /f .\SomeDirectory
    start .                        & REM Launches explorer.exe for current directory
    <Command> | clip               & REM Redirects output to Windows clipboard
    clip < <FileName>              & REM Copies content of <FileName> onto Windows clipboard
    
File and Directory Operations
    
    cat .\somefile.txt
    rename file1.txt file2.txt     & REM Renames file1.txt to file2.txt
    rename *.txt *.doc             & REM Renames all .txt files to .doc files
    move <source> <dest>           & REM Moves one or more files (supports pattern)
    mkdir FooDirectory
    
System Operations
    
    ipconfig                       & REM Displays TCP/IP network configuration values
