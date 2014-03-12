Telerik.Sitefinity.Samples.Testimonials
=======================================

The Testimonials sample project is a simple user widget-based module for maintaining a list of testimonials that are submitted by users. The Testimonials sample demonstrates how to create and install a basic intra-site module, based on a user wiget.

### Requirements

* Sitefinity 6.3 license

* .NET Framework 4

* Visual Studio 2012

* Microsoft SQL Server 2008R2 or later versions


### Installation instructions: SDK Samples from GitHub

1. Clone the [Telerik.Sitefinity.Samples.Dependencies](https://github.com/Sitefinty-SDK/Telerik.Sitefinity.Samples.Dependencies) repo to get all assemblies necessary to run for the samples.
2. Fix broken references in the class libraries, for example in **SitefinityWebApp** and **Telerik.Sitefinity.Samples.Common**:

  1. In Solution Explorer, open the context menu of your project node and click _Properties_.  
  
    The Project designer is displayed.
  2. Select the _Reference Paths_ tab page.
  3. Browse and select the folder where **Telerik.Sitefinity.Samples.Dependencies** folder is located.
  4. Click the _Add Folder_ button.


3. In Solution Explorer, navigate to _SitefinityWebApp_ -> *App_Data* -> _Sitefinity_ -> _Configuration_ and select the **DataConfig.config** file. 
4. Modify the **connectionString** value to match your server address.

### Integrate the OpenAccess enhancer

Sitefinity ships with OpenAccess ORM. To use OpenAccess in the data provider of a module, you must integrate the OpenAccess enhancer. To do this:

1. Open SitefinityWebApp folder.
2. From the context menu of the project **TestimonialsWebsite**, click _Unload Project_.
3. From the context menu of the unloaded project, click _Edit TestimonialsWebsite.csproj_.
4. Find the **<ProjectExtensions>** tag and replace it with the following lines of code: 
```xml
<ProjectExtensions>
  <VisualStudio>
    <UserProperties OpenAccess_EnhancementOutputLevel="1" OpenAccess_UpdateDatabase="False" OpenAccess_Enhancing="False"OpenAccess_ConnectionId="DatabaseConnection1" OpenAccess_ConfigFile="App.config" />
  </VisualStudio>
</ProjectExtensions>
<PropertyGroup>
  <OpenAccessPath>C:\GitHub\Telerik.Sitefinity.Samples.Dependencies</OpenAccessPath>
</PropertyGroup>
<Import Condition="Exists('$(OpenAccessPath)\OpenAccess.targets')" Project="$(OpenAccessPath)\OpenAccess.targets" />
```

5. In the **OpenAccessPath** element, place the path to the folder containing the **OpenAccess.targets** file. 

    This is the location of the **Telerik.Sitefinity.Samples.Dependencies** repository that you cloned locally. In the example above, the repository is cloned in **C:\GitHub**.
    
6. Save the changes.
7. From the context menu of the project, click _Reload Project_.

    **NOTE**: If you are using Sitefinity 4.0 SP1 or prior, see [Custom Modules for Sitefinity 4.0](http://www.sitefinity.com/documentation/documentationarticles/developers-guide/sitefinity-essentials/modules/creating-custom-modules/custom-modules-for-sitefinity-4-0).
8. Build the solution.

### Login

To login to Sitefinity backend, use the following credentials: 

**Username:** admin

**Password:** password


### Additional resources

[Car rental demo](http://demos.telerik.com/aspnet-ajax/carrental/)

