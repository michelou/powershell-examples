# <span id="top">PowerShell Modules</span> <span style="size:30%;"><a href="../README.md">⬆</a></span>

**WIP**

<pre style="font-size:80%;">
<b>&gt; <a href="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pwsh" rel="external" title="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pwsh">pwsh</a> -c "<a href="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/get-module" rel="external" title="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/get-module">Get-Module</a> -ListAvailable -Name *Power*| <a href="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-object" rel="external" title="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-object">Select-Object</a> -Property Name,Version,Path"</b>

Name                                      Version
----                                      -------
<a href="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.archive">Microsoft.PowerShell.Archive</a>              1.2.5    (PowerShell 7)
Microsoft.PowerShell.Diagnostics          7.0.0.0  (PowerShell 7)
Microsoft.PowerShell.Host                 7.0.0.0  (PowerShell 7)
Microsoft.PowerShell.Management           7.0.0.0  (PowerShell 7)
Microsoft.PowerShell.PSResourceGet        1.2.0    (PowerShell 7)
Microsoft.PowerShell.Security             7.0.0.0  (PowerShell 7)
Microsoft.PowerShell.ThreadJob            2.2.0    (PowerShell 7)
Microsoft.PowerShell.Utility              7.0.0.0  (PowerShell 7)
PowerShellGet                             2.2.5    (PowerShell 7)
Microsoft.PowerShell.Operation.Validation 1.0.1    (Windows PowerShell)
PowerShellGet                             1.0.0.1  (Windows PowerShell)
Microsoft.PowerShell.LocalAccounts        1.0.0.0  (Windows PowerShell)
</pre>

We display [`PowerShellGet`][powershellget] commands whose name matches `'*Module*'` as follows :

<pre style="font-size:80%;">
<b>&gt; <a hef="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pwsh" rel="external" title="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pwsh">pwsh</a> -c "<a href="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/get-module" rel="external" title="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/get-module">Get-Module</a> -ListAvailable -Name <a href="https://learn.microsoft.com/en-us/powershell/module/powershellget" rel="external" title="https://learn.microsoft.com/en-us/powershell/module/powershellget">PowerShellGet</a> | % { $_.ExportedCommands.Values } | <a href="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/where-object" rel="external" title="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/where-object">Where-Object</a> { $_.CommandType -eq 'Function' -and $_.Name -like '*Module*'} | <a href="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-object" rel="external" title="https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-object">Select-Object</a> -Property CommandType,Name,Version"</b>

CommandType Name                  Version
----------- ----                  -------
   Function <a href="https://learn.microsoft.com/en-us/powershell/module/powershellget/find-module">Find-Module</a>           2.2.5
   Function Get-InstalledModule   2.2.5
   Function Install-Module        2.2.5
   Function Publish-Module        2.2.5
   Function <a href="https://learn.microsoft.com/en-us/powershell/module/powershellget/save-module">Save-Module</a>           2.2.5
   Function Uninstall-Module      2.2.5
   Function Update-Module         2.2.5
   Function <a href="https://learn.microsoft.com/en-us/powershell/module/powershellget/update-modulemanifest">Update-ModuleManifest</a> 2.2.5<span style="color:darkgrey;">
   Function Install-Module        1.0.0.1
   Function Find-Module           1.0.0.1
   Function Save-Module           1.0.0.1
   Function Update-Module         1.0.0.1
   Function Publish-Module        1.0.0.1
   Function Get-InstalledModule   1.0.0.1
   Function Uninstall-Module      1.0.0.1
   Function Update-ModuleManifest 1.0.0.1</span>
</pre>

***

*[mics](https://lampwww.epfl.ch/~michelou/)/June 2026* [**&#9650;**](#top)
<span id="bottom">&nbsp;</span>

<!-- link refs -->
[powershellget]: https://learn.microsoft.com/en-us/powershell/module/powershellget "https://learn.microsoft.com/en-us/powershell/module/powershellget"
