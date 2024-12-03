# Command Prompt commands
| Function | Command | Notes |
|:---:|---|---|
| Delete desktop.ini recursively | `del /s /q /f /a ".\desktop.ini" ` | deletes from current and subdirectories |
| Download GroupPolicyEditor for Homer users | `FOR %F IN ("%SystemRoot%\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientTools-Package~*.mum") DO (DISM /Online /NoRestart /Add-Package:"%F")`<br><br> `FOR %F IN ("%SystemRoot%\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientExtensions-Package~*.mum") DO (DISM /Online /NoRestart /Add-Package:"%F")` |
| Folder Junction | `mklink /J link target` |
| Foreach line in file do | `for /F "usebackq delims=" %i in ("file.txt") do echo %i` |
| Convert/Compress video to h.265 (FFMPEG) | `ffmpeg -i "source.mp4" -c:v libx265 -preset slow -b:v 0 -c:a aac -b:a 0 "target.mp4"` | use `hevc_nvenc` instead of `libx265` for faster GPU encoding, but less efficiency
Recursive ffmpeg | `for /r %i in (*) do if /i "%~xi"==".MP4" ffmpeg -i %i -c:v libx265 -c:a aac "%~dpi%~ni-x265%~xi"` | `/r`: recursive<br>`/i`: case insensitive<br>`%i`: variable name<br>`%~xi`: extension name<br>`%~dpi`: directory path<br>`%~ni`: file name

# PowerShell commands
| Function | Command | Notes |
|:---:|---|---|
| Unblock files | `Get-ChildItem -Path . \| Unblock-File` | unblocks all files under current directory<br>replace `-Path .` to `-Path "C:\..."` to unblock another directory |  
