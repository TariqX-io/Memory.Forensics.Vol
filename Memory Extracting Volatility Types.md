# Memory.Forensics.Vol

### Windows Memory Extracting
The method of extraction for memory differs depending on the OS we are analyzing. For Windows, there are two tools that are commonly used in the industry: FTK and WinPmem. That is not to say that these are the only two superior or used tools during an investigation. Tool selection is largely a matter of preference. Other notable tools include MAGNET RAM, Velociraptor, and F-Response.

`FTK` and `WinPmem` are both great tools that have their own use case. FTK is a forensics suite used to extract data from disk images, but it also includes the ability to create memory images. WinPmem is a lightweight and portable open-source memory acquisition tool, so copying the executable to the victim host is relatively easy.

Once you've extracted a memory image from a Windows system, irrespective of the tool used, you will then load that memory image into an analysis tool. While there are many commercial forensics tools that support memory analysis, the most popular option in an open source tool called Volatility. More on that in a moment.

---

### Linux Memory Extracting
Unfortunately, extracting memory on Linux can be a fair bit more complicated than on Windows, and you may need to go through a few additional steps before obtaining your memory image. First, there's the matter of the memory profile.

In the context of memory forensics, a "profile" refers to a set of rules and data structures that define the format of a specific operating system's memory. For instance, the architecture for an OS dump with specifications like 10x64 Build:10.0.15063.0 differs significantly from from that of 10.0.10586.306. In order for analysis tools like Volatility to parse a memory image accurately, the target profile for the source system must already be in Volatility's database. Otherwise, you will need to rebuild the memory profile, which consists of creating a new memory profile or modifying an existing one to correctly interpret and analyze the contents of the memory image. This can be very tedious. While this same issue can arise for Windows memory images, it is more common for Linux due to the diversity of distributions, kernels, and unique customizations available.

For the purposes of this lab, we will focus on extracting memory from Windows.

---

### Memory Analysis using Volatility
When it comes to analyzing the output of a memory extraction, Volatility remains the preferred favorite of many forensics professionals. Volatility is an open-source command line-based memory forensics framework composed of purpose-built modules, referred to in Volatility as plug-ins. Each plug-in is designed to provide a specific functionality for extracting and analyzing information from memory dumps.

When running Volatility, a user will specify both the memory dump image name and the plug-in to be run. The standard syntax for Volatility version 3 (Vol3) is as follows:

```
python vol.py -f <imagename> <plugin>
```
---

Although Volatility can display its output directly in the command line, a best practice is to save the output to a text file, which allows you to easily refer back to it later or use other tools like NotePad++ to analyze the output. An example of a complete Volatility command is as follows:

```
Python vol.py -f image.raw windows.info.Info > imageinfo.txt
```

Below are some of the most commonly used plug-ins for Volatility:

* `windows.info.Info` - Get OS information
* `windows.pstree.PsTree` - List  process within a tree structure relationship
* `windows.pslist.PsList` - List all processes
* `windows.cmdline.CmdLine` - Display process command-line arguments
* `Windows.netscan` - Displays open network connections


