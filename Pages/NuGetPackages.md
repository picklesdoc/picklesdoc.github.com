# NuGet Packages

## Pickles.MSBuild

This package includes a [MSBuild Task](MSBuildTask) for generating Pickles documentation, and a build target to assist in adding to your project. 

### Build Target

The NuGet package includes a default build target provides documentation generation, configurable via MSBuild properties.

The following properties are supported:

| MSBuild Property               | Description                                                                      | Default
|--------------------------------|----------------------------------------------------------------------------------|-------------------------------------------------------------
| Pickles_Generate               | True or False whether or not to run the build target and generate documentation. | False 
| Pickles_FeatureDirectory       | The path to your project's directory containing SpecFlow features. [See Pickles documentation](ArgumentsFeatureDirectory) | $(MSBuildProjectDirectory)\Features 
| Pickles_OutputDirectory        | The Pickles documentation output directory. This directory will be removed if it exists, and recreated. [See Pickles documentation](ArgumentsOutputDirectory) | $(MSBuildProjectDirectory)\pickles-site
| Pickles_DocumentationFormat    | [Documentation format](ArgumentsDocumentationFormat)                             | [See Pickles documentation](ArgumentsDocumentationFormat)
| Pickles_ResultsFormat          | [Results format](ArgumentsTestResultsFormat)                                     | [See Pickles documentation](ArgumentsTestResultsFormat)
| Pickles_ResultsFile            | [Results file](ResultsFile)                                                      | [See Pickles documentation](ResultsFile)
| Pickles_SystemUnderTestName    | [System under test name](ArgumentsSystemUnderTestName)                           | [See Pickles documentation](ArgumentsSystemUnderTestName) 
| Pickles_SystemUnderTestVersion | [System under test version](ArgumentsSystemUnderTestVersion)                     | [See Pickles documentation](ArgumentsSystemUnderTestVersion)

#### Example 1 - Configuration via .csproj

One way to control the build target is to add properties to your .csproj file:

    <PropertyGroup>
        <Pickles_Generate>True</Pickles_Generate>
        <Pickles_DocumentationFormat>dhtml</Pickles_DocumentationFormat>
        <Pickles_OutputDirectory>C:\Temp\MyDocumentation</Pickles_OutputDirectory>
    </PropertyGroup>


#### Example 2 - Configuration via MSBuild 

Build target properties can also be passed to MSBuild via command-line argument. 

    msbuild /p:Pickles_Generate=True /p:Pickles_DocumentationFormat=dhtml /p:Pickles_OutputDirectory=C:\Temp\MyDocumentation
    
