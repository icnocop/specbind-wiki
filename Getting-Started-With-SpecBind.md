## What is SpecBind?

SpecBind is an extension to SpecFlow that uses common language steps to allow a user to define interaction with an appliction. Unlike conventional specflow where the user needs to define how each step definition interacts with the host system, SpecBind uses conventions and a thin page model to minimize coding efforts and maximize flexibility when defining the link between specifications and working sites.

## Initial Setup

Getting SpecBind installed is a simple process:

1. Go to www.specflow.org and follow the instructions for installing the Visual Studio Extension
2. Choose the driver type you want to use to interact with the host system:
	* CodedUI (Recommended)
	* Watin
3. Create a new test project in Visual Studio, Make it a Coded UI project if you are using that.
4. Install the NuGet package for SpecBind

`PM> Install-Package SpecBind.CodedUI`

And you're done! Follow the Starting your SpecBind Project section to begin creating tests, or Understanding SpecBind Steps for more explaination on how to work with SpecBind.