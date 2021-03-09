# Enumerate users
``` powershell
$users=(net user /domain)
$users -match "\S+" -replace "`n|`r","abc" -split "\s+" | ? { $_.trim() -ne "" } | Out-File -FilePath "[Path]\users.txt"
```

