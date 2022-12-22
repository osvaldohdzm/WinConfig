NVIM commands for long files
:set nowrap

pip install jsontool :%!python -m json.tool --no-ensure-ascii

:%!python3 -m json.tool --no-ensure-ascii

:syntax off

this is not necesari owithoy sintax off :set re=0

paste with *p or "*p

:syntax off :syntax on

type dirty.json | python -m json.tool > pretty.json

Change tab
gt


:set nowrap :%!python -m json.tool --no-ensure-ascii :set re=0

paste with *p

:syntax off :syntax on

type dirty.json | python -m json.tool > pretty.json

### Configuration file

:help nvim-config


copy from clipboard
"+y
"*p
$XDG_CONFIG_HOME/nvim/init.vim


## Usar vim plug

mkdir C:\Users\osvaldohm\AppData\local\nvim\
mkdir C:\Users\osvaldohm\AppData\local\nvim\init.vim
mkdir C:\Users\osvaldohm\AppData\local\nvim\plugged

Install plug
iwr -useb https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim |`
    ni "$(@($env:XDG_DATA_HOME, $env:LOCALAPPDATA)[$null -eq $env:XDG_DATA_HOME])/nvim-data/site/autoload/plug.vim" -Force

Edit file:
nvim C:\Users\osvaldohm\AppData\Local\nvim\init.vim

copy
https://raw.githubusercontent.com/EduarCuri/my_init.vim/master/init.vim

Install:
nvim .\init.vim

PlInstallOlCleanPlUpdate


Del python from:
C:\Users\osvaldohm\AppData\Local\Microsoft\WindowsApps

Refresh with:
$env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path","User")

Create sumboli link python3:
New-Item -Path C:\LinkDir -ItemType SymbolicLink -Value F:\RealDir

Install neovim python
pip3 install neovim --user





C:\Users\osvaldohm\.ssh>
create config file
Host *
    ServerAliveInterval 40



``` 
Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'
```

``` 
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
``` 

``` 
New-ItemProperty -Path "HKLM:\SOFTWARE\OpenSSH" -Name DefaultShell -Value "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" -PropertyType String -Force
```

```
# Start the sshd service
Start-Service sshd

# OPTIONAL but recommended:
Set-Service -Name sshd -StartupType 'Automatic'

# Confirm the Firewall rule is configured. It should be created automatically by setup. Run the following to verify
if (!(Get-NetFirewallRule -Name "OpenSSH-Server-In-TCP" -ErrorAction SilentlyContinue | Select-Object Name, Enabled)) {
    Write-Output "Firewall Rule 'OpenSSH-Server-In-TCP' does not exist, creating it..."
    New-NetFirewallRule -Name 'OpenSSH-Server-In-TCP' -DisplayName 'OpenSSH Server (sshd)' -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22
} else {
    Write-Output "Firewall rule 'OpenSSH-Server-In-TCP' has been created and exists."
}
```








```
echo "Install fonts"
$fonts = (New-Object -ComObject Shell.Application).Namespace(0x14)
foreach ($file in gci *.ttf)
{
    $fileName = $file.Name
    if (-not(Test-Path -Path "C:\Windows\fonts\$fileName" )) {
        echo $fileName
        dir $file | %{ $fonts.CopyHere($_.fullname) }
    }
}
cp *.ttf c:\windows\fonts\
```




Install-Module PSReadLine -Force



Get-PoshThemes

Set-ExecutionPolicy Unrestricted
oh-my-posh font install



set cascaydia font icons powershrll




Check RDP enaled:
$rdpEnabled = 0 -eq (Get-ItemPropertyValue 'HKLM:\SYSTEM\CurrentControlSet\Control\Terminal Server' fDenyTSConnections)



SSH SOCK5 proxy 
ssh kali@8.tcp.ngrok.io -p 18347 -D 8080

8080 is localhost 
proxy is


no command 
 ssh kali@8.tcp.ngrok.io -p 18347 -D 8080 -N

locahost:8080 settings internet NOT basic internet 
advanced lan
and enable sock5





```
set-itemproperty -path "hkcu:Software\Microsoft\Windows\CurrentVersion\Internet Settings" -name ProxyEnable -value 1
set-itemproperty -path "hkcu:Software\Microsoft\Windows\CurrentVersion\Internet Settings" -name ProxyServer -value "socks=localhost:8080;" -type string


set-itemproperty -path "hkcu:Software\Microsoft\Windows\CurrentVersion\Internet Settings" -name ProxyEnable -value 0
Remove-ItemProperty -path "hkcu:Software\Microsoft\Windows\CurrentVersion\Internet Settings" -name ProxyServer
```

