# Release Process

1. Check the version number in project.build (/src/Pickles/VersionInfo.cs will be updated during build)
1. Open a command line and run "release.cmd"
1. Create a [release](https://github.com/picklesdoc/pickles/releases/) on GitHub
   1. with release notes
   1. tag it with 'vx.y.z' where x is the major version, y the minor version and z the revision number
   1. Upload "$/deploy/pickles-x.y.z.0.zip" to the release
1. Close the 'vx.y' milestone and create a new one
1. Push the nuget packages from myget to nuget gallery
1. Update the picklesdoc website to point to the new version
1. Generate outputs with new version and add to website
1. Make an announcement on pickles-dev group.
1. Tweet using @PicklesDoc
 