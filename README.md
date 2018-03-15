# Quandis Business Objects 4

## Project Configuration

qbo4 implements patterns and practices as discrete modules, rather than as a monolithic software stack.

- qbo4 client modules will be made available as NuGet packages on http://api.nuget.org
- qbo4 server modules (our primary intellectual property) will be made available as NuGet packages on https://nuget.quandis.net


### NUGET configuration

To reference existing qbo4 Nuget packages, add http://nuget.quandis.net as a NuGet source 
- In Visual Studio, Tools > Nuget Package Manager > Package Manager Settings > Package Sources
- Name: `nuget.quandis.net`, Source: `http://nuget.quandis.net/nuget`

To add qbo4 modules to the nuget.quandis.net feed:
- Ensure `nuget.exe` is installed (Typically to `c:\program files(x86)\nuget`)
- From Visual Studio's the Package Manager console, cd to a project's folder
- Create a spec: 
  - `& 'C:\Program Files (x86)\NuGet\Nuget.exe' spec`
  - edit the {project}.nuspec file as you see fit
- Package the project:
  - `dotnet pack qbo4.{propject}.csproj /p:Version={version}`
  - this will create a {project}.{version}.nupgk file in the compiled output folder (/bin/debug)
- Publish the package:
  - From Powershell:
    > ```nuget.exe push C:\...\{project}.{version}.nupkg {apiKey} -Source http://nuget.quandis.net/nuget```
  - From VS Package Manager Console:
    > ```dotnet nuget push C:\...\{project}.{version}.nupkg -k {apikey} -s http://nuget.quandis.net/nuget```
  - contact CTO for an apiKey


