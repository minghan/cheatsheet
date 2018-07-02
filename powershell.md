PowerShell
==========

    Get-Help Get-Help

Print all env vars:

    Get-Childitem env:

Cat a file

    Get-Content .\file.txt

Replace text in a file

    $config = Get-Content somefile.xml
    $config | % { $_.Replace("FOO", $foo) } | % { $_.Replace("BAR", $bar) } | Set-Content somefile.xml

Process Management

    get-process

Measure time of a command

    measure-command { . someprog.exe /param1 }
    
Cmdlets

    Get-Module

    # Get cmdlets in a module
    Get-Command -Module <ModuleName>

Working with .NET objects

    # Create new .NET object
    $date = New-Object System.DateTime

    [Guid]::Parse("MyGuid")

    # List property names
    $obj | Get-Member

    # List property names and values
    $obj | Select-Object -Property *
