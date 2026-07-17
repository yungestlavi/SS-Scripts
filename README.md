# SS-Scripts
### Very often it happens that during a ScreenShare (SS) users disable the clipboard, so that they do not allow us to copy and paste from the SSer's pc to the user's pc, scripts or commands useful for carrying out the SS, for this reason I have created a repository with many scripts that can be useful during an SS, so as to have them all in one place without looking for them everywhere.

## Services script (by github.com/praiselily)

```
powershell Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass && powershell Invoke-Expression (Invoke-RestMethod https://raw.githubusercontent.com/praiselily/lilith-ps/refs/heads/main/Services.ps1) 
```

## BAM

**Redlotus BAM**

```
powershell Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass && powershell Invoke-Expression (Invoke-RestMethod https://raw.githubusercontent.com/PureIntent/ScreenShare/main/RedLotusBam.ps1)
```

## Analyzer Mod

### Habibi Mod Analyzer (by
```
powershell -command "irm 'https://raw.githubusercontent.com/HadronCollision/PowershellScripts/refs/heads/main/HabibiModAnalyzer.ps1' | iex"
```

### Tonynoh Mod Analyzer (by github.com/meowtonynoh)

```
powershell -ExecutionPolicy Bypass -Command "Invoke-Expression (Invoke-RestMethod 'https://raw.githubusercontent.com/MeowTonynoh/MeowModAnalyzer/main/MeowModAnalyzer.ps1')"
```
## Journal commands (and what they do)

**Cacls**

Cacls is a prefetch bypass method that involves changing the security settings of the ‪C:\Windows\Prefetch folder.
This command shows all security changes that have occurred in the prefetch folder

```
fsutil usn readjournal c: csv | findstr /i /C:"0x00000800" /i /C:"0x80000800" | findstr /i /C:"Prefetch" > Cacls.txt
```
**JnativeHook**

JnativeHook is a string used by autoclickers, when an autoclicker is opened, jnativehook string goes in the %temp% folder.
This command scan the NTFS for JnativeHook flags

```
fsutil usn readjournal c: csv | findstr /i /C:"JnativeHook" | findstr /i /C:".dll" > JnativeHook.txt
```
**Python Executions**

This command scans for all python files executed in the pc (in instance)

```
fsutil usn readjournal C: csv | findstr /i /C:".py" >> PyFilesExecuted.txt
```
**Batch Executions**
This command scans for all batch (.bat) files executed  in the pc (in instance)

```
fsutil usn readjournal C: csv | findstr /i /C:".bat" >> BatFilesExecuted.txt
```
**Prefetch**

This command scans the journal for possible .pf modifications in the ‪C:\Windows\Prefetch folder.

```
fsutil usn readjournal c: csv | findstr /i /C:"0x80000200" /i /C:"0x00001000" /i  /C:"0x00002000" | findstr /i /C:".pf"  > Prefetch.txt
```
**Deleted files**
This command scans the journal for every file deletion of the following extensions:
.exe, .jar, .dll, .pf, .ps1, .py, .bat, JnativeHook

```
fsutil usn readjournal c: csv | findstr /i /C:"0x80000200" | findstr /i /C:".exe" /C:".pf" /C:".jar" /C:".py" /C:".bat" /C:".ps1" /C:"JnativeHook" /C:".dll" > Deleted.txt
```
**Renamed files**

This command scans the journal for every file renames of the following extensions:
.exe, .jar, .dll, .pf, .ps1, .py, .bat, JnativeHook


```
fsutil usn readjournal c: csv | findstr /i /C:"0x00001000" | findstr /i /C:"0x00002000" | findstr /i /C:".exe" /C:".pf" /C:".jar" /C:".py" /C:".bat" /C:".ps1" /C:"JnativeHook" /C:".dll" > Renamed.txt
```
**AHK**
This command scans the journal for every .ahk file modifications

```
fsutil usn readjournal c: csv | findstr /i /C:".ahk" > AHK.txt
```

**ALl files modifcations**
This command scans the journal for every file modifications of the following extensions
.exe, .jar, .dll, .pf, .ps1, .py, .bat, JnativeHook

```
fsutil usn readjournal c: csv | findstr /i /C:"0x80000200" /i /C:"0x00001000" /i  /C:"0x00002000" | findstr /i /C:".pf" /i /C:".exe" /i /C:".bat" /i /C:".cmd" /i /C:".jar" /i /C:".bat" /i /C:".pif" /i /C:"jnativehook" /i /C:"?" > all.txt
```


