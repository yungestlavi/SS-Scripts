# SS-Scripts
Very often it happens that during a ScreenShare (SS) users disable the clipboard, so that they do not allow us to copy and paste from the SSer's pc to the user's pc, scripts or commands useful for carrying out the SS, for this reason I have created a repository with many scripts that can be useful during an SS, so as to have them all in one place without looking for them everywhere.

Services script (by github.com/praiselily)

```powershell Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass && powershell Invoke-Expression (Invoke-RestMethod https://raw.githubusercontent.com/praiselily/lilith-ps/refs/heads/main/Services.ps1) ```

Analyzer Mod

Habibi Mod Analyzer (by
``` powershell -command "irm 'https://raw.githubusercontent.com/HadronCollision/PowershellScripts/refs/heads/main/HabibiModAnalyzer.ps1' | iex" ```

Tonynoh Mod Analyzer (by github.com/meowtonynoh)

``` powershell -ExecutionPolicy Bypass -Command "Invoke-Expression (Invoke-RestMethod 'https://raw.githubusercontent.com/MeowTonynoh/MeowModAnalyzer/main/MeowModAnalyzer.ps1')" ```
