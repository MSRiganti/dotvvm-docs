## Create a new project (Command Line)

If you don't have Visual Studio, you can create a new DotVVM project from the command line using .NET Core templates.

### Install the template

First, you need to install the `dotnet new` template for DotVVM from NuGet. To do this, run the following command in the console:

```
dotnet new -i DotVVM.Templates::*
```

Please note that this command can take few minutes to execute.

### Run the template

When the template is installed, you can run it in an empty directory. The tooling will create a project there:

```
mkdir ProjectName
cd ProjectName
dotnet new dotvvm
```

### DotVVM Command Line syntax

The project generated by the template contains a reference to `DotVVM.CommandLine` package.

You can invoke it by calling `dotnet dotvvm ...`. You can use one of the following commands to perform the following tasks:

<table class="table table-bordered">
    <tr>
        <th>Task</th>
        <th>Short Syntax</th>
        <th>Long Syntax</th>
        <th>Options</th>
    </tr>
    <tr>
        <td>Create Page</td>
        <td><code>dotnet dotvvm ap</code></td>
        <td><code>dotnet dotvvm add page</code></td>
        <td>
            <ul>
                <li><code>{PageName}</code> - name of the page or path of the `.dothtml` file</li>
                <li><code>-m {MasterPage}</code> - (optional) name or path of the master page</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Create Master Page</td>
        <td><code>dotnet dotvvm am</code></td>
        <td><code>dotnet dotvvm add master</code></td>
        <td>
            <ul>
                <li><code>{PageName}</code> - name of the page or path of the `.dotmaster` file</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Create Markup Control</td>
        <td><code>dotnet dotvvm ac</code></td>
        <td><code>dotnet dotvvm add control</code></td>
        <td>
            <ul>
                <li><code>{ControlName}</code> - name of the control or path of the `.dotcontrol` file</li>
                <li><code>-c</code> - (optional) create a code-behind file for the control</li>
            </ul>
        </td>
    </tr>
</table>

### Examples

1. Create the `Views/Site.dotmaster` master page:

```
dotnet dotvvm add master Site
```

2. Create the `Views/Page1.dothtml` page and embed it in the `Views/Site.dotmaster`:

```
dotnet dotvvm add page Page1 -m Site
```

3. Create the `Controls/MyControl.dotcontrol` user control with the code behind file:

```
dotnet dotvvm add control Controls/MyControl.dotcontrol -c
```


