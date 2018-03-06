# Quandis Business Objects 4

## Project Configuration

qbo4 implements a patterns and practices as dicrete modules, rather than as a monolithic software stack.

- qbo4 modules will be made available as NUGET packages on http://nuget.quandis.net


### NUGET confiruation

To reference existing qbo4 Nuget packages, add http://nuget.quandis.net as a NUGET source 
- In Visual Studio, Tools > Nuget Package Manager > Package Manager Settings > Package Sources
- Name: `nuget.quandis.net`, Source: `http://nuget.quandis.net/nuget`

To add qbo4 modules to the nuget.quandis.net feed:
- Ensure `nuget.exe` is installed (Typically to `c:\program files(x86)\nuget`)
- From Visual Studio's the Package Manager console, cd to a project's folder
- Create a spec: 
  - `& 'C:\Program Files (x86)\NuGet\Nuget.exe' spec`
  - edit the {project}.nuspec file as you see fit
- Package the project:
  - `dotnet pack qbo4.{propject}.csproj`
  - this will create a {project}.{version}.nupgk file in the compiled output folder (/bin/debug)
- Copy the .nupkg to the `c:\inetput\nuget\packages` folder of the `http://nuget.quandis.net` server


