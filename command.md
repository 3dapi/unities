# Powershell
## rename
``` powershell
  dir | Rename-Item -NewName {$_.name -replace "source", "target"}
```
