# MSBuild Task

To allow Pickles to integrate right into your build process there is an MSBuild task provided.  You can use this right in your Visual Studio projects or separate MSBuild .proj files.

## Referencing the Task

After you have downloaded Pickles you will need to place the Pickles.MSBuild.Tasks.dll assembly somewhere on your disk (if you are using continuous integration then make sure it is somewhere in your working folder).  You then get access to the Pickles task by including this at the top of your .proj file:

	<UsingTask AssemblyFile=".\path\to\Pickles.MSBuild.Tasks.dll" TaskName="Pickles" />

## Using the Task

The task is very simple to use.  Simply add a target and call the Pickles task from within like so:

    <Target Name="document">
        <MakeDir Directories="$(OutputDirectory)" />
        <Pickles FeatureDirectory="$(FeatureDirectory)" OutputDirectory="$(OutputDirectory)" />
    </Target>

## Sample

See the Pickles.Sample project for an example of using this task in real life.