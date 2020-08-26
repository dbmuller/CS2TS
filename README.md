# CS2TS
C# to Typescript model converter

Put the T4 file in the project that has the classes you want to convert from C# to TS

Fill in the details about your project

Make sure the project is built so the script has access to the Assembly

Run!

Files are output into the project and directory of choice - one model per file

## Finding the FQ assembly name

You can run the developer command prompt, run ILDASM, and inspect the details
https://docs.microsoft.com/en-us/dotnet/framework/tools/ildasm-exe-il-disassembler

## Known issues

### Could not load file or assembly 'System.Runtime, Version = 4.2.0.0'

This is a visual studio "bug" with running T4 templates and reflection and need to add the System.Runtime reference into your devenv.exe.config

See this post
https://developercommunity.visualstudio.com/idea/535990/filenotfoundexception-systemruntime-version4210-wh.html

Solution here on SO:
https://stackoverflow.com/questions/51550265/t4-template-could-not-load-file-or-assembly-system-runtime-version-4-2-0-0

Default location for Visual Studio 2019
C:\Users\\[user]\AppData\Local\Microsoft\VisualStudio\16.0_37dd0e65

Add in
```
<dependentAssembly>
  <assemblyIdentity name="System.Runtime" publicKeyToken="b03f5f7f11d50a3a" culture="neutral"/>
  <bindingRedirect oldVersion="0.0.0.0-5.0.0.0" newVersion="4.0.0.0"/>
</dependentAssembly>
```
