# 如何使用PowerShell脚本为WSL挂载硬盘

⚠️ 对于legacy powershell版本，保持文件时，务必选择 `UTF BOM` 格式。

```shell
# 此脚本如果不是以管理员身份运行，将自动以管理员权限重启。

# 1. 检查当前是否具备管理员权限
$currentPrincipal = New-Object Security.Principal.WindowsPrincipal([Security.Principal.WindowsIdentity]::GetCurrent())
$isElevated = $currentPrincipal.IsInRole([Security.Principal.WindowsBuiltInRole]::Administrator)

if (-not $isElevated) {
    Write-Host "正在尝试以管理员权限重新启动脚本..." -ForegroundColor Yellow
    
    $arguments = '-NoProfile -ExecutionPolicy Bypass -File "{0}"' -f $PSCommandPath
    
    try {
        Start-Process -FilePath 'powershell.exe' -ArgumentList $arguments -Verb RunAs
        exit
    }
    catch {
        Write-Host "无法获取管理员权限，操作已取消。" -ForegroundColor Red
        Write-Host "按任意键退出..."
        $null = $Host.UI.RawUI.ReadKey("NoEcho,IncludeKeyDown")
        exit
    }
}

# ------------------------------------------------------------------------------------------------------
# 脚本已确认具备管理员权限，开始执行主逻辑

# 配置参数
$TargetDiskID = "✏️改成你要挂载的disk id"

# 界面初始化
$Host.UI.RawUI.WindowTitle = "WSL 挂载工具 (管理员)"
$Host.UI.RawUI.BackgroundColor = "DarkBlue"
$Host.UI.RawUI.ForegroundColor = "White"
Clear-Host

Write-Host "脚本当前正以管理员权限运行。" -ForegroundColor Green
Write-Host "------------------------------------------------" -ForegroundColor Gray

# 1. 获取磁盘对象
$DiskToMount = Get-Disk | Where-Object { $_.UniqueID -eq $TargetDiskID }

if ($null -ne $DiskToMount) {
    # 2. 构造物理路径
    $DevicePath = "\\.\PHYSICALDRIVE" + $DiskToMount.Number
    Write-Host "检测到目标磁盘: $DevicePath" -ForegroundColor Cyan
    Write-Host "UniqueID: $TargetDiskID" -ForegroundColor Gray

    # 3. 在 WSL 中挂载
    Write-Host "正在向 WSL 发送挂载指令..." -ForegroundColor Yellow
    
    # 执行命令并合并错误流
    $mountResult = wsl.exe --mount $DevicePath --bare 2>&1

    if ($LASTEXITCODE -eq 0) {
        Write-Host "`n[成功] 磁盘已成功挂载到 WSL。" -ForegroundColor Green
    }
    else {
        Write-Host "`n[错误] WSL 报错:" -ForegroundColor Red
        Write-Host $mountResult -ForegroundColor Red
    }
}
else {
    Write-Host "`n[错误] 未找到对应磁盘！" -ForegroundColor Red
    Write-Host "无法找到 ID 为 '$TargetDiskID' 的磁盘。" -ForegroundColor Yellow
    Write-Host "提示: 请运行 'Get-Disk | Select Number, UniqueID' 核对。" -ForegroundColor Gray
}

# 结束脚本
Write-Host "`n操作完成。按任意键退出..." -ForegroundColor Gray
$null = $Host.UI.RawUI.ReadKey("NoEcho,IncludeKeyDown")
```
