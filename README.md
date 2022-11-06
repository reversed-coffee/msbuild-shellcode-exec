# msbuild-shellcode-exec

Shellcode execution through msbuild.exe using inline tasks.

## Description

This is a proof of concept for executing shellcode via MSBuild. It works by
abusing inline tasks.

The process is as follows:
- The inline code gets compiled by MSBuild
- MSBuild executes the code
- The running code executes the shellcode by hijacking a managed thread that it
creates

## Prerequisites

* Visual Studio 2022 (or any version of MSBuild that supports inline tasks)

## Usage

Open powershell in the base directory and run this command:

```powershell
& "C:\Program Files\Microsoft Visual Studio\2022\Community\Msbuild\Current\Bin\msbuild.exe" ShellcodeExec.csproj
```

Technically, you can use any version of MSBuild that supports inline tasks, and you don't need to use PowerShell to run it. You could run MSBuild from the command prompt, or you could use a batch file to run it. Whatever floats your boat.

A video example of this is shown below:\
[![YouTube Video](https://img.youtube.com/vi/26EM24Bcksw/mqdefault.jpg)](https://www.youtube.com/watch?v=26EM24Bcksw)

## Disclaimer

This source is for educational purposes only. Do not use this maliciously. I am
not responsible for any damage caused by this project.