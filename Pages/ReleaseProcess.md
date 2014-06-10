# Release Process

1. Update ReleaseNotes.md to include the new release
	1. Release Number
	2. Date 
	3. New Feature(s) if any
	4. Bug(s) Fixed if any 
1. Check the version number in project.build (/src/Pickles/VersionInfo.cs will be updated during build)
1. Open a command line and run "release.cmd"
1. Create a [release](https://github.com/picklesdoc/pickles/releases/) on GitHub
   1. with release notes
   1. tag it with 'vx.y.z' where x is the major version, y the minor version and z the revision number
   1. Upload "$/deploy/pickles-x.y.z.zip" to the release
1. Generate outputs with new version and add to website
1. Update the picklesdoc website to point to the new version
1. Push the nuget packages from myget to nuget gallery
1. Make an announcement on pickles-dev group.
1. Tweet using @PicklesDoc
 