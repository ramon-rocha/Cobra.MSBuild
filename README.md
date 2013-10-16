Cobra.MSBuild
===========
This is a MSBuild task and targets file that adds support for building Cobra
projects (.cobraproj files) using MSBuild from Microsoft .NET or XBuild from
Xamarin Mono.

Compiling
---------------
To compile from the command line enter:

    cobra -c -t:lib -out:targets/Cobra.MSBuild.dll CobraCompiler.cobra

Alternatively, build ```Cobra.MSBuild.cobraproj``` using the
MonoDevelop.CobraBinding addin.

On Mono, you must first apply the CommandLineBuilder patch to
```path/to/mono/mcs/class/Microsoft.Build.Utilities/Microsoft.Build.Utilities/CommandLineBuilder.cs```
in order to compile the build task.

A precompiled assembly is also provided for convenience.  Remember to backup
your existing copy in case you need to revert!

Testing
----------
To test, run ```msbuild``` or ```xbuild``` on the solution or one of the
projects in the test_projects folder.

Alternatively, create a new Cobra project using MonoDevelop and add this
line at the end of the ```.cobraproj``` file:

    <Import Project="..\..\..\targets\Cobra.targets" />

TODO
---------
  - Finish patch and submit to Mono project
  - Alter Cobra.targets to support embedded resources on Mono
  - Override CobraCompiler.LogEventsFromTextOutput method to capture warnings and errors on Mono (regex in base class doesn't capture Cobra messages)
  - Support RootNamespace compiler option (coordinate with MD addin to not break code completion and tooltips)
  - Update MD addin project templates to import Cobra.targets

