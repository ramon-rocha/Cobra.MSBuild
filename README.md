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

Testing
----------
To test, run ```msbuild``` or ```xbuild``` on the solution or one of the
projects in the test_projects folder.

Alternatively, create a new Cobra project using MonoDevelop and add this
line at the end of the ```.cobraproj``` file:

    <Import Project="path\to\targets\Cobra.targets" />

TODO
---------
  - Override CobraCompiler.LogEventsFromTextOutput method to capture warnings and errors on Mono (regex in base class doesn't capture Cobra messages)
  - Support RootNamespace compiler option (coordinate with MD addin to not break code completion and tooltips)
  - Update MD addin project templates to import Cobra.targets

