# Release Process

We denote versions with x.y.z where x is the major version, y the minor version and z the revision number

1. Update ReleaseNotes.md to include the new release
	1. Release Number
	2. Date 
	3. New Feature(s) if any
	4. Bug(s) Fixed if any 
1. Check the version number in build.fsx
1. Open a command line and run "build.bat"
2. go to the deploy folder and unzip pickles-x.y.z.zip
3. Test the runners
	1. testOutput.cmd x.y.z
	2. "\Program Files (x86)\MSBuild\12.0\Bin\MSBuild.exe" testOutput.proj /p:Version=x.y.z
	3. testOutput.ps1 x.y.z
1. Create a [release](https://github.com/picklesdoc/pickles/releases/) on GitHub
   1. called vx.y.z 
   1. with release notes
   1. tag it with 'vx.y.z' on branch release
   1. Upload "$/deploy/pickles-x.y.z.zip" to the release
1. Generate outputs with new version and add to website
	1. Note: Dita format should be zipped
1. Update the picklesdoc website to point to the new version
1. Push the nuget packages from myget to nuget gallery
1. Make an announcement on pickles-dev group.
1. Tweet using @PicklesDoc
 