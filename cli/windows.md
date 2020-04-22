### List all services that do not run as a standard account
Get-ItemProperty -Path Registry::HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\* | Where-Object {($_.ObjectName -notlike 'NT Authority\*') -and ($_.ObjectName -ne $null) -and ($_.ObjectName -ne "LocalSystem")}
