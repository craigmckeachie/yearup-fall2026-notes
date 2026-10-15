Tired of explaining Windows Defender exclusions?  Me too:
---
Windows users, when you open a project in IntelliJ, you may see a **Microsoft Defender** message asking you to **exclude the project folder from antivirus scanning to improve performance**. This appears because Defender scans the files Java creates while building your program, which can slow things down.
This setup is optional. It applies the setting IntelliJ is asking for to your entire pluralsight folder, covering all your current and future projects at once. Reducing this scanning can make builds faster. Defender will skip scanning everything inside that folder, so keep it dedicated to coursework.
If you don’t have administrator access (e.g. a YUU machine), you can contact IT Help.

```
844-493-2787
ITHelp@yearup.org
```

1. Open **Start** and search for **Windows PowerShell**.
2. Select **Run as administrator** and approve the permission prompt..
3. Copy and paste this entire block, then press Enter:.

    ```shell 
    $folder = Join-Path $env:USERPROFILE 'pluralsight'
    Add-MpPreference -ExclusionPath $folder -ErrorAction Stop
    (Get-MpPreference).ExclusionPath | Where-Object { $_ -eq $folder }
    ```

You should see your folder’s full path printed, such as C:\Users\alex\pluralsight, confirming that the exclusion was added.
**If you need someone else’s administrator login:** replace the first line with your own folder’s actual path before running it—for example:

  ```shell
  $folder = 'C:\Users\alex\pluralsight'
  ```