# The Quick Guide to OpenSim Unit Testing

## Running Tests

### Linux:

```sh
 nant test
```

This will print out to the console the test state.

### Windows

See the TESTING ON WINDOWS section below.

## Writing Tests

Tests are written to run under NUnit. For more information on NUnit, please see: [http://www.nunit.org/index.php](http://www.nunit.org/index.php)

## Adding Tests

Tests should not be added to production assemblies. They should instead be added to assemblies of the name
`My.Production.Assembly.Tests.dll`. This lets them easily be removed from production environments that don't want the bloat.

Tests should be as close to the code as possible. It is recommended that if you are writing tests they end up in a "Tests" sub-directory
of the directory where the code you are testing resides.

If you have added a new test assembly that hasn't existed before, you must list it in both `.nant/local.include` and `.nant/bamboo.build`
for it to be accessible to Linux users and to the continuous integration system.

## More Details

The tests are contained in certain DLLs. At the time of writing, these DLLs have tests in them:

- OpenSim.Region.ScriptEngine.Common.Tests.dll
- OpenSim.Region.ScriptEngine.Shared.CodeTools.Tests.dll
- OpenSim.Region.ScriptEngine.Shared.Tests.dll
- OpenSim.Framework.Tests.dll
- OpenSim.Region.CoreModules.dll
- OpenSim.Region.Physics.OdePlugin.dll[2]

The console command used to run the tests is `nunit-console` (or `nunit-console2` on some systems). This command takes a listing of DLLs to inspect for tests.

Currently Bamboo's[3] build file (.nant/bamboo.build) lists only those DLLs for nunit-console to use. However, it would be equally correct to simply pass in all DLLs in bin/. Those without tests are just skipped.

The nunit-console command generates a file TestResults.txt by default. This is an XML file containing a listing of all DLLs inspected, tests executed, successes, failures, etc. If nunit-console is passed in all DLLs in bin/, this file bloats with test results for DLLs that have no tests.

[2] OpenSim.Region.Physics.OdePlugin.dll is not tested with NUnit as it uses a different physics engine.

[3] Bamboo is a continuous integration server used to automate the build and testing process of software projects. It can be found at [http://www.bamboo-ci.org/](http://www.bamboo-ci.org/).

## TESTING ON WINDOWS

To run NUnit tests on Windows, you will need to have .NET 2.0 installed. The default version of nunit-console is compatible with .NET 2.0.

### Running Tests via Command Line

To run tests, open a command prompt and navigate to the directory containing your test DLLs. Then, run one of the following commands:

```sh
nunit-console2 OpenSim.Framework.Tests.dll
```

or

```sh
nunit-console OpenSim.Framework.Tests.dll
```

### Running Tests via NUnit-GUI

You can also use NUnit-GUI to run tests. Simply open NUnit-GUI and add your test DLLs to the list. You can then run all tests at once or select individual tests to run.

## Using NUnit Directly

The NUnit project is a very mature testing application. It can be obtained from [www.nunit.org](http://www.nunit.org/) or via various package distributions for Linux. Please ensure you get a .NET 2.0 version of NUnit, as OpenSim makes use of .NET 2.0 functionality.

NUnit comes with two tools that will enable you to run tests from assembly inputs:

- NUnit-GUI: A graphical user interface for running tests.
- NUnit-Console: A command-line tool for running tests.

### Running Tests via NUnit-Console

To run tests using the NUnit-Console tool, open a command prompt and navigate to the directory containing your test DLLs. Then, run one of the following commands:

```sh
nunit-console2 OpenSim.Framework.Tests.dll  # On Linux
nunit-console OpenSim.Framework.Tests.dll    # On Windows
```

### Running Tests via NUnit-GUI

To run tests using the NUnit-GUI tool, open NUnit-GUI and add your test DLLs to the list. You can then run all tests at once or select individual tests to run.
