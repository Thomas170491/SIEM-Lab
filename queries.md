# Detection Queries used in Lab

## Suspicious PowerShell execution

``
ḱql
    event.code: "1" AND process.name: "powershell.exe" AND (
      process.args: "-EncodedCommand" OR
      process.args: "-enc" OR
      process.args: "-ExecutionPolicy" OR
      process.args: "Bypass" OR
      process.args: "-NoProfile" OR
      process.args: "-WindowStyle" OR
      process.args: "Hidden"
    )
  ```
## Office application spawnning Powershell

```ḱql
    event.code : "1" AND process.name: "powershell.exe" and (
    process.parent.name: "winword.exe" OR
    process.parent.name: "excel.exe" OR
    process.parent.name: "outlook.exe" OR
    process.parent.name "powerpoint.exe"
   )
  ```

## Failed logins
``ḱql
event.category: authentification AND event.outcome: failure
  ```
