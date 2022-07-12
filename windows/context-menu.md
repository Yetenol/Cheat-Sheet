<h1> Context menu </h1>

[⌂](../README.md) › [Windows](../README.md#windows) ›

```powershell
regedit
```

1. Open registry path `HKEY_CLASSES_ROOT\Directory\shell\IntelliJ IDEA`
1. Right click on `shell` and select `New > Key`
1. Type in name of action (can be anything)
1. Right Click on your new Key and add another new Key
1. Name new Key `command` (mandantory)
1. Click on command and right click on `(Default)`, then click Modify...
1. Set Value Data to your Intellij IDEA program location plus `%1` 
   - e.g: `"C:\Program Files\JetBrains\IntelliJ IDEA 2021.2.1\bin\idea64.exe" "%V"`
2. Click on the Key you made in step 6 and set `(Default)` value to the text you want to see
3. Go to your folder and Enjoy!
4. Also, if you want an icon, do this:
    - Go to the Key you made in step 6
    - Right Click and choose `New > String Value`
    - Name it `Icon` (mandantory)
    - Right Click > Modify...
    - Set Data Value to Intellij IDEA exe file

# Sources

- 2022-05-02: [Open a project in IntelliJ from folder - Stack Overflow](https://stackoverflow.com/questions/49733733/open-a-project-in-intellij-from-folder)