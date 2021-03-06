# FluentMigrator DNX Runner

A DNX runner for [Fluent Migrator](https://github.com/schambers/fluentmigrator/).

## Installing

### As a project dependency

The nupkg is [on Nuget.org](https://www.nuget.org/packages/FluentMigrator.Runner.DNX), so
simply run:

```powershell
dnu install FluentMigrator.Runner.DNX
```

And add the command with name `FluentMigrator.Runner.DNX` to your project.

Or add the runner to your project manually, here is an example project.json:

````json
{
    "version": "1.0.0-*",
    "dependencies": {
        "FluentMigrator": "1.5.1",
        "FluentMigrator.Runner.DNX": "1.0.0-*"
    },
    "frameworks": {
        "dnx451": { }
    },
    "commands": {
        "migrate": "FluentMigrator.Runner.DNX"
    }
}
````

Or use the Package Manager in Visual Studio.

### As a DNX tool

DNX provides a way to install global tools using the `dnu commands install` command. Simply run:

````powershell
dnu commands install FluentMigrator.Runner.DNX
````

You will then have the `fm` tool available for you on the command line. The syntax is the same as if you had added the `migrate` command
described above on the dependency install.

If you use it as a tool you don't need to make any changes to the `project.json` file, you simply need the `FluentMigrator` dependency, so
you can reference its API to create migrations. No need to add the `FluentMigrator.Runner.DNX` dependency or the command to that file.

## Running

If you simply run `dnx migrate` the command line options will show up for you

````powershell
dnx . migrate --provider sqlserver2012 --connectionString <yourconnectionstring>
````

If you installed it as a global command, simply run the `fm` command:

````powershell
fm --provider sqlserver2012 --connectionString <yourconnectionstring>
````

Here are all the options:

````
Usage:
    dnx . run --provider PROVIDER --connectionString CONNECTION [--assembly ASSEMBLY] [--output FILE] [--task TASK] [--migrateToVersion VERSION] [--profile PROFILE] [--tag TAG] [--verbose]
    dnx . run --version
    dnx . run --help
````

## Maintainer

* [Giovanni Bassi](http://blog.lambda3.com.br/L3/giovannibassi/), aka Giggio, [Lambda3](http://www.lambda3.com.br), [@giovannibassi](http://twitter.com/giovannibassi)

Contributors can be found at the [contributors](https://github.com/giggio/FluentMigrator.Runner.DNX/graphs/contributors) page on Github.

## Contact

I am only on Jabbr most of the day, usually on the [ASP.NET vNext room](https://jabbr.net/#/rooms/AspNetvNext), with user name `Giggio`.

## License

This software is open source, licensed under the Apache License, Version 2.0.
See [LICENSE.txt](https://github.com/code-cracker/code-cracker/blob/master/LICENSE.txt) for details.
Check out the terms of the license before you contribute, fork, copy or do anything
with the code. If you decide to contribute you agree to grant copyright of all your contribution to this project, and agree to
mention clearly if do not agree to these terms. Your work will be licensed with the project at Apache V2, along the rest of the code.
