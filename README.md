# fpp
Find Program Path: iterate through the `PATH` environment variable to search for the given programs

## Description

 `fpp` returns the path names of the files (or links) which would be executed in the current environment.  It does this by searching the `PATH` for executable files matching the names of the arguments.
 This program also searches for over **30** extensions such as `.exe`, `.ps1`, `.sh`, `.py`, etc.

## Download

Binaries for Windows, MacOS, and Linux can be found on the [Releases Page](https://github.com/jftuga/fpp/releases) -- expand the `Assets` to see the downloads.

## Usage

```
Usage: fpp [OPTION]... [FILE]...
Find Program Path: Iterate through the PATH environment variable to search for the given programs

  -p    show all paths and then exit
  -v    show program version and then exit
```

## Install From Source

```
go get github.com/jftuga/fpp
cd fpp
go build -ldflags="-s -w"
./fpp (or .\fpp.exe)
```

## Examples

```
Notice that 'curl' appears 3 times and 'notepad' appears twice...

PS C:\github.com\jftuga\fpp> .\fpp.exe curl notepad compmgmt
C:\Windows\system32\curl.exe
C:\Windows\system32\notepad.exe
C:\Windows\system32\compmgmt.msc
C:\Windows\notepad.exe
C:\Users\john\scoop\shims\curl.exe
C:\Users\john\scoop\shims\curl.ps1
```

```
pi@rpi3:~/fpp $ ./fpp curl ping4 rg gettext
WARNING: '/usr/local/bin' appears multiple times in PATH
/usr/local/bin/rg
/usr/bin/curl
/usr/bin/gettext
/usr/bin/gettext.sh
/bin/ping4
```
