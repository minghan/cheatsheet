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
