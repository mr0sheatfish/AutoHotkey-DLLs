# AutoHotkey-DLLs
### DLL files for easy implementation of the AutoHotKey engine in projects in different languages.
____
### To register Dll Library in Windows: 
1. Move one of these dlls to directory (*AutoHotkey_x32\*.dll*)"%windir%\System32" for x32 or (*AutoHotkey_x64\*.dll*)"%windir%\SysWOW64" for x64
2. Use Win+R or Command Propmt to type this for register Dll Library for easy access: `%windir%\System32\regsvr32.exe %windir%\System32\AutoHotkey_x32*.dll` or `%windir%\SysWOW64\regsvr32.exe %windir%\SysWOW64\AutoHotkey_x64*.dll`.
3. Reboot your system.
4. Enjoy
____
### You can see all AutoHotkey*.dll functions via utility dumpbin.exe with parameter /export
Developer Command Prompt: `dumpbin /export ..\AutoHotkey*.dll`
____
### Example to manual import to C#:
```C#
[DllImport("AutoHotkey*.dll", CallingConvention = CallingConvention.Cdecl, CharSet = CharSet.Unicode, EntryPoint = "ahkdll")]
    private static extern int ahkdll(
    [MarshalAs(UnmanagedType.LPWStr)] string scriptFilePath, 
    [MarshalAs(UnmanagedType.LPWStr)] string parameters = "", 
    [MarshalAs(UnmanagedType.LPWStr)] string title = "");

[DllImport("AutoHotkey*.dll", CallingConvention = CallingConvention.Cdecl, CharSet = CharSet.Unicode, EntryPoint = "ahktextdll")]
    private static extern int ahktextdll(
        [MarshalAs(UnmanagedType.LPWStr)] string script,
        [MarshalAs(UnmanagedType.LPWStr)] string parameters =  "",
        [MarshalAs(UnmanagedType.LPWStr)] string title = "");
```
____
#### Stolen from [HotKeyIt/ahkdll](https://github.com/HotKeyIt/ahkdll-v1-release)
