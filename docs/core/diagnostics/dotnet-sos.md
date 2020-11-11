---
title: dotnet-sos - .NET Core
description: Learn how to install and use the dotnet-sos command-line tool.
ms.date: 08/26/2020
---
# SOS installer (dotnet-sos)

**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions

## Install dotnet-sos

To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:

```dotnetcli
dotnet tool install -g dotnet-sos
```

Starting from .NET 5, it is now possible to directly download a one-file executable for your operating system:

- Win ([x86](https://aka.ms/dotnet-sos/win-x86) | [x64](https://aka.ms/dotnet-sos/win-x64) | [arm](https://aka.ms/dotnet-sos/win-arm) | [arm-x64](https://aka.ms/dotnet-sos/win-arm64))
- macOS ([x64](https://aka.ms/dotnet-sos/osx-x64))
- Linux ([x64](https://aka.ms/dotnet-sos/linux-x64) | [arm](https://aka.ms/dotnet-sos/linux-arm) | [arm64](https://aka.ms/dotnet-sos/linux-arm64) | [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) | [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64))

## Synopsis

```console
dotnet-sos [-h|--help] [options] [command]]
```

## Description

The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS. Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.

## Options

- **`--version`**

  Displays version information.

- **`-h|--help`**

  Shows command-line help.

## dotnet-sos install

Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes. On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup. If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.

### Synopsis

```console
dotnet-sos install
```

## dotnet-sos uninstall

Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.

### Synopsis

```console
dotnet-sos uninstall
```
