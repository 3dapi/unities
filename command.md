# Powershell
## rename
``` powershell
  dr | Rename-Item -NewName {$_.name -replace "source", "target"}
```
