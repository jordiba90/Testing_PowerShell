----
----

# Testing_PowerShell
Source: https://abdus.dev/posts/powershell-file-metadata-guide/

----
----

**1) Getting File Properties**

- ls | Get-Member -MemberType Property
- ls *txt | Get-Member -MemberType Property

**2) Changing File Properties**

- ls *txt # Get-ChildItem
- $set_date=Get-date

    **2.1) Changing File Properties: one file**

  - (ls *txt .\a*).LastWriteTime=$set_date # (Get-ChildItem *txt .\a*).LastWriteTime=$new_date
  - (ls *txt .\a*).LastWriteTime.ToString("dd/MM/yyyy H:mm:ss") # (Get-ChildItem *txt .\a*).LastWriteTime.ToString("dd/MM/yyyy H:mm:ss")
  - ls *txt # Get-ChildItem

    **2.2) Changing File Properties: multiple files**

  - $old_date="2023-01-01 00:00"
  - ls *txt|%{$_.LastWriteTime=$old_date} # Get-ChildItem|ForEach-Object {$_.LastWriteTime=$old_date}
  - ls *txt # Get-ChildItem

| ![image](https://github.com/jordiba90/Testing_PowerShell/assets/45982544/46ffbd42-6189-4e69-a0ef-220b0d61b20c) |
|-|

----
