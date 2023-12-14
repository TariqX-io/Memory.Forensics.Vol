### Analyze Memory with Volatility

---

#### Step 1
  * Open the `Volatility developer` file or your `program file for Volatility`.
  * Locate the `Volatility python script` to verify it is in the file.

#### Step 2 
  * In the Command Prompt window, type:
```
cd [File Path of Volatility developer folder]
```
  * and press Enter to navigate to the Volatility folder.

#### Step 3
  * At the command prompt, type:
```
python [Name of volatility python script] -h
```
  * and press Enter to display the help guide for Volatility.
  * On this screen, you should see a number of configurability options for Volatility, as well as a list of the available plug-ins and their purpose. In the next steps, we will be using the `windows.info.Info, windows.pstree.PsTree, windows.netscan.NetScan, and windows.dlllist.DllList` plug-ins. Take a moment to locate each plug-in in the help guide and review the description.
    * **windows.info.Info** : Shows OS and kernel details of the memory sample being analyzed
    *  **windows.pstree.PsTree** : Plugin for listing processes in a tree based on their parent process ID.
