### Get-MachineAccountQuotaUsers.ps1
Gets a list of AD computers that were created by regular users exercising their default right to create up to 10 computer accounts in an AD domain

```
$machineAccountQuotaComputers = Get-ADComputer -filter {ms-DS-CreatorSID -ne "$null"} -Properties ms-DS-CreatorSID,Created

foreach ($machine in $machineAccountQuotaComputers) {
    $creator = $null
    try {
        $creator = [System.Security.Principal.SecurityIdentifier]::new($machine.'ms-DS-CreatorSID').Translate([System.Security.Principal.NTAccount]).Value
    }
    catch {
        $creator = $machine.'ms-DS-CreatorSID'
    }

    New-Object psobject -Property @{
        Name = $machine.Name
        DistinguishedName = $machine.DistinguishedName
        Creator = $creator
        Created = $machine.Created
    } | Select-Object Name,DistinguishedName,Creator,Created | Sort-Object -Property Created
}
```

https://gist.github.com/dstreefkerk/377c063bd3083e2c6eecf3f7afdbf6da
