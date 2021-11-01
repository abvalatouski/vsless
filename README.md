# VS-less

Visual Studio eats terabytes of RAM! The repository tries to help you to avoid
opening that beast, providing some console utilities.

## Scripts

###  `asprun`

Download the script with:

```console
powershell -c "Invoke-WebRequest -Outfile asprun.bat -Uri https://raw.githubusercontent.com/abvalatouski/vsless/master/asprun.bat"
```

Shortened help message:

```text
Runs an ASP.NET project at the specified port and prints its URL.
The launched process can be stopped via 'taskkill /f /im project.exe',
if its name matches name of the project.

    asprun project [/?] [/p port] [/c buildconfig] [/s] [/o] [/q]

Options

    project         Path to the project's folder. 

    /p port         Defaulted to 5001.      

    /c buildconfig  Either Debug or Release.
                    Defaulted to Debug.     

    /s              Print URL of Swagger UI.

    /o              Open URL in the browser.

    /q              Disable URL printing.

    Options can be placed in any order.
    In case of duplication newer options will override older ones.
    Unknown option will be treated as a project path.

Example

    mkdir WeatherForecast
    dotnet new webapi -o WeatherForecast
    asprun WeatherForecast /s /o
    taskkill /f /im WeatherForecast.exe
```
