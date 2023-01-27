Flow Debugger Service requires a minimum of Microsoft .NET 6.0.13.

To find the version of the framework that is installed:

1. On the Start menu, choose `Run`.
1. In the open box, enter `regedit.exe`. You must have administrative credentials to run regedit.exe.
1. In the Registry Editor, open the subkey `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\dotnet\Setup\InstalledVersions\x64\sharedfx\Microsoft.NETCore.App`.
1. If the folder `Microsoft.NETCore.App` is not present, or the subkey name is a version inferior to `6.0.13`, then you do not have the required version or .NET 6.0 installed.
1. If it is not installed, continue with the following steps to install it.

To install .NET 6.0.13:

1. Download the [NET&nbsp;6.0.13][NET 60] installer.
1. Double-click on the installer file to run it.
1. Follow the wizard to complete the installation.

[NET 60]: {{< url "MSDotNet.60.MainDoc" >}}