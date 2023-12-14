### Capture Memory with Winpmem

---

#### Step 1
  * On the Desktop, open the `Tools folder`, then `shift-right-click the Winpmem_mini_x64_rc2.exe application` and select `Copy as path` to save the `Winpmem` application's file path to the clipboard.

#### Step 2
  * Click the `Start menu and type cmd`, then right-click the `Command Prompt` result and select `Run as administrator` to launch a Command Prompt window with administrator privileges.

#### Step 3
  * At the command prompt, type:
```
cd C:\[folder path]
```

  * and press Enter to navigate to the Evidence folder.

#### Step 4
  * At the command prompt, right-click to paste the `Winpmem file path`, then type `winmem.raw` and press Enter to run the Winpmem application, saving the output to the Evidence folder as a file titled winmem.raw.
  * Command should look similar to this:

```
[Destination folder path]>"[Folder path of the winpmem executable]" winmem.raw
```

**PICTURE FOR AN EXAMPLE**
![image](https://github.com/TariqX-io/Memory.Forensics.Vol/assets/105884880/a24a9a30-a287-4178-adae-1636a21cc2c1)

#### Step 5
  * When the memory capture is complete, type `dir` and press Enter to display the contents of the Evidence directory.
  * You should see `two MEM files` saved here. You should also see that the sizes of the dump are roughly same. As mentioned in the Core Concepts lesson, choosing an acquisition tool is largely a matter of preference.
