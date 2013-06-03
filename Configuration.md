The core behavior of SpecBind can be configured through .NET configuration files. The configuration has to be placed in a file called *App.config*.

## Default Configuration

The NuGet packages that come with SpecBind will create a default configuration file entry that contains most of the primary information needed to run.
The following sample demonstrates what the SpecBind section will contain after installing the CodedUI package. 

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <section name="specBind" type="SpecBind.Configuration.ConfigurationSectionHandler, SpecBind"/>
  </configSections>
  <specBind>
    <browserFactory provider="SpecBind.CodedUI.CodedUIBrowserFactory, SpecBind.CodedUI" browserType="IE" />
  </specBind>
</configuration>
```

The following example shows all possible configuration options with their default values (the config section definition has been omitted for better readability).

```xml
<specBind>
    <application startUrl="{application URL}" />
    <browserFactory provider="{provider assembly name}" browserType="IE" />
</specBind>
```
### Configuration Elements
#### `<appliction>`
This section can be used to define specific settings for the application to use when it begins testing.

<table>
    <tr>
        <th>Attribute</th>
        <th>Value</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>startUrl</td>
        <td>A browser URL (http://myapp.com)</td>
        <td>The base address of the application being tested.
            This will be combined with the application page addresses 
            for navigation and validation.</td>
    </tr>
</table>

#### `<browserFactory>`
This section can be used to define which back-end provider is being used to link the steps to the application being tested. 

<table>
    <tr>
        <th>Attribute</th>
        <th>Value</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>provider</td>
        <td>The assembly name of the provider.</td>
        <td>The fully qualified assembly type of the provider. This should be installed by the NuGet package.</td>
    </tr>
	<tr>
        <td>browserType</td>
        <td>The type of browser to start for web testing. (IE)</td>
        <td>The ID of the browser type to start. Values vary by the provider, but basics ones are (IE, Chrome and FireFox).</td>
    </tr>
</table>
