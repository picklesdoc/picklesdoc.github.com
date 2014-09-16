# How to set up Pickles on Teamcity?

Some of the reasons for creating a living documentation system is creating a shared understanding between developers and business people and giving constant feedback. Most business people don't understand code, but with Pickles you can easily provide a more useful test report for them. Such as this one:

![](../Images/TeamCityHowTo/scenarios_teamcity.PNG)

**Note**: Here we use NUnit test execution reports, however Pickles supports also MSTest, XUnit and SpecRun. To use another test runners adjust parameters accordingly.

First you need to either add required files to your test project or install required tools on the server where your TeamCity agent is running. The latter is not recommended approach, because it might cause problems if multiple projects use the same agents.
The required tools are: Pickles, Specflow and NUnit (or other test runner).
The following picture presents the list of files that have to be included in the project:

![](../Images/TeamCityHowTo/required_files.png)


Specflow is complied for .NET 3.5, so if your project uses .NET 4.0, remember to create Specflow.exe.config file with the following content: 

      <?xml version="1.0" encoding="utf-8" ?> 
      <configuration> 
      <startup> 
        <supportedRuntime version="v4.0.30319" /> 
      </startup> 
      </configuration>
