# The Gold Standard in .NET Development

It is a rare luxury when one gets to stand atop years of success, only to re-shape what the future holds. That is exactly where .NET finds itself - relishing years of developer loyalty, while pivoting itself to a position for upcoming success. At this key inflection point in the history of .NET, some specific focus areas define the gold standard in .NET development going forward. This whitepaper dives into the new capabilities of .NET -- including fundamental improvements and standardization efforts surrounding it -- to bring forth the best in breed ideas for modern .NET development.

## State of .NET

The very first beta of the .NET Framework was released 17 years ago. The .NET Framework -- originally called 'Next Generation Windows Services' (NGWS) -- was an attempt to combine together the APIs and system level abstractions that most Windows applications needed. The next two decades saw the .NET Framework flourish by leaps and bounds -- there is almost no development technology parallel to the kind of success, loyalty, love, and growth has enjoyed.

With time, the .NET Framework grew in features and more abstractions that make life easy for developers. The developer community stepped up to build a rich ecosystem around it, resulting in fantastic tools, language support, and a mature framework to build Windows apps on. Enterprises, large and small, bought into the .NET promise and made big bets with apps built on top of the .NET technology stack. Developers flourished in the .NET ecosystem, with ever increasing sophistication of tools that aid in building polished apps.

### Why Pivot?  

With all the advancements over the last 15 years, the .NET Framework grew and grew. This was very convenient for developers, but it represented a giant framework nonetheless. This presented a new challenge since various apps across web/desktop/mobile platforms started depending on the same foundation. Updates became increasingly difficult and the ecosystem started becoming fragile -- it was clearly time for a change.

A lot has changed in the software industry during the lifetime of .NET. The mobile revolution has changed the way we interact with software, cloud computing has turned hardware infrastructure into a service and cheaper computing has lead to exponential growth of technology. Machine learning is paving the way for software intelligence and portability across platforms is of utmost importance. We truly live in a "cloud-first" and "mobile-first" world now. 

With this new era of computing, .NET had to evolve to support the next generation of apps - step out of just Windows, support multiple platforms and focus on portability. For .NET to remain relevant for developers, it had to be reinvented - a critical pivot that will set up .NET for success over the next decade. In differential calculus, an inflection point is a point on a curve at which the curve changes from being concave to convex. .NET was at its inflection point - thankfully a pivot sets it up nicely for the future!

[Insert Inflection]

### Behold the New

Let's take a look at the bigger picture, as we stand today.

![](https://i.imgur.com/nakIiTQ.png)

This isn't your grandma's .NET and not your grandpa's tooling. No offense to grandparents, but things have changed a lot in the .NET landscape. There are several flavors of .NET now - [.NET Framework](https://en.wikipedia.org/wiki/.NET_Framework), [.NET Core](https://en.wikipedia.org/wiki/.NET_Framework#.NET_Core), [Mono](https://en.wikipedia.org/wiki/Mono_(software)), [Unity](https://en.wikipedia.org/wiki/Unity_(game_engine)) and other Base Class Libraries (BCLs) - all catering specific app platforms towards the developer's benefit. 

The giant monolitic framework still exists -- the .NET Framework -- and it still runs all Windows desktop, web, and mobile apps. .NET Core is the new kid on the block, written from ground up, lean, modular, and sporting a cross-platform Common Language Runtime (CLR). The implications of .NET Core are huge - for the first time, .NET apps can run natively outside of Windows, on Mac and Linux. Xamarin apps still run on Mono - which is a long-standing open source port of .NET to other platforms. With today's .NET, developers can target virtually any app platform and any device family - the opportunities are endless. The recent release of .NET Core 2.0 has big implications for the future of .NET and tooling going forward.

Along with the changes in .NET offerings, .NET development tools have also evolved. Visual Studio has various flavors and lowers the barrier to entry with a more "come-as-you-are" mindset. On Windows, Visual Studio has become synonymous with .NET development - the one IDE where developers often spend their entire days. Visual Studio has come a long way as an IDE - from a giant behemoth to a carefully crafted streamlined IDE catering to specific development workflows. The Visual Studio feature richness continues though - it is the ubiquitous IDE to build modern web, desktop, mobile, cloud and future-facing solutions.

A few years back, you would probably laugh if someone told you that Visual Studio would run natively on a Mac - but that's the reality today. [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/) is a full-featured native IDE and brings most of the VS development comforts over to MacOS - for modern mobile, web and cloud development. Then there is [Visual Studio Code](https://code.visualstudio.com/) - a beautiful light-weight truly cross-platform code editor. Modern .NET developers aren't shy of using the Command Line either - the one thing common across all development platforms. And .NET obliges by providing solid .NET CLI tooling for consistent cross-platform usage. 

### Why Standards?

Most .NET developers are likely not doing just one type of development - there may be some desktop development through WinForms/WPF or modern web development with ASP.NET Core or cross-platform mobile apps with Xamarin. Wouldn't it be nice if platform-independent code artifacts could be shared across various .NET platforms? 

.NET, as we mentioned, comes in several flavors now - .NET Framework, .NET Core, Mono, Unity and other BCLs - all catering specific app platforms. Customized .NET flavors are great, but come with the obvious risk of fragmentation. To .NET developers, this should all be transparent - there is an obvious need for unification and code reusability across various .NETs. There is also some need to unify [XAML](https://en.wikipedia.org/wiki/Extensible_Application_Markup_Language) - the UI markup language used across various .NET platforms. Let's talk standardization!

## .NET Standard

[.NET Standard](https://github.com/dotnet/standard) is a formal specification of .NET APIs that is intended to be available on all supporting .NET implementations - a way of conformity. The motivation behind .NET Standard is simple - have greater uniformity in the .NET ecosystem and allow for code portability/reuse.

![](https://i.imgur.com/c6hvROc.png)

You may ask, "What about [Portable Class Libraries](https://docs.microsoft.com/en-us/dotnet/standard/cross-platform/cross-platform-development-with-the-portable-class-library) (or PCLs)?" PCLs had the same promise of portability across platforms, however, implementations suffered as the number of PCL profiles increased. Developers were made to choose device families and pick the lowest common denominator across supported APIs. 

.NET Standard is the next generation idea on portability - putting the API implementation responsibilities back on .NET platforms. While PCLs let developers code to the lowest common denominator of APIs available in supported platforms, .NET Standard takes a different route. The onus is now on the app platforms to implement .NET APIs. When your app supports a certain .NET Standard, you are guaranteed all APIs in that version of .NET Standard to be supported in all supporting app platforms. The goal of .NET Standard is two fold:

* Define a uniform set of Base Class Library (BCL) APIs across all implementations of .NET, irrespective of workload or platform execution environment.
* Enable developers to write portable libraries that are usable across .NET implementations, using the defined set of APIs.

The various .NET implementations target specific versions of .NET Standard. Each .NET version essentially advertises the highest .NET Standard version it supports, which also means it supports previous versions. With the [release of .NET Standard 2.0](https://blogs.msdn.microsoft.com/dotnet/2017/08/14/announcing-net-standard-2-0/), .NET Core gets a lot of the feature parity with the full .NET Framework in terms of APIs. 

### Better Portability

You can get a glimpse of the different implementations of .NET and their support of corresponding .NET Standard versions - things are moving along nicely. All this means more portability of .NET code and libraries for developers - reuse all things from a developer's perspective.

|.NET Standard|[1.0]|[1.1]|[1.2]|[1.3]|[1.4]|[1.5]|[1.6]|    [2.0]|
|:-------------------------------------|---------:|------:|--------:|-------:|--------:|----------------:|--------------:|---------:|
|.NET Core|1.0|1.0|1.0|1.0|1.0|1.0|**1.0**|**2.0**|
|.NET Framework|4.5|**4.5**|**4.5.1**|**4.6**|4.6.1|4.6.1|4.6.1|**4.6.1**|
|Mono|4.6|4.6|4.6|4.6|4.6|4.6|**4.6**|**5.4**|
|Xamarin.iOS|10.0|10.0|10.0|10.0|10.0|10.0|**10.0**|**10.14**|
|Xamarin.Mac|3.0|3.0|3.0|3.0|3.0|3.0|**3.0**|**3.8**|
|Xamarin.Android|7.0|7.0|7.0|7.0|7.0|7.0|**7.0**|**8.0**|
|Universal Windows Platform|10.0|10.0|10.0|10.0|**10.0**|vNext|vNext|**vNext**|
|Windows|8.0|**8.0**|**8.1**||||||
|Windows Phone|8.1|8.1|**8.1**||||||
|Windows Phone Silverlight|**8.0**||||||||

[1.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.0.md
[1.1]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.1.md
[1.2]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.2.md
[1.3]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.3.md
[1.4]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.4.md
[1.5]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.5.md
[1.6]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.6.md
[2.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard2.0.md

Note: Bold text indicates when a .NET implementation added support for a given .NET Standard version.

The common APIs for the .NET Framework and Xamarin were used as a basis for .NET Standard. With .NET Standard 2.0, this surface extends across the .NET ecosystem forming a Base Class Library of over 32000 APIs. These additions make it much easier to port existing code over to .NET Standard - there are API analyzers to help developers bring their code over to be .NET Standards comliant. Since .NET Standard acts as a BCL API definition, additional Framework Class Libraries can provide platform specific functionality - on top of their support for a specific .NET Standard version. Because of this moving, existing applications to frameworks that use .NET Standard implementations gets much easier.

### .NET Standard Dependency

A developers time is valuable - maintaining a long lists of APIs or profiles to adhere to .NET Standard isn't efficient. Managing .NET Standard compliance in a project is extremely simple - instead of requiring the individual dependencies that make up .NET Standard, a single reference is used.

```xml
<Project Sdk="Microsoft.NET.Sdk"> 
  <PropertyGroup> 
    <TargetFramework>netstandard2.0</TargetFramework> 
  </PropertyGroup> 
</Project>
```

The single reference to `<TargetFramework>netstandard2.0</TargetFramework>` in a .csproj file provides the API definitions needed for your application. This works because the reference to netstandard is a meta-package. The netstandard package does not contain any dlls, but instead references other packages required by the application. Only packages that satisfy the .NET Standard implementation for the platform your application targets will be added to the project. Therefore the same netstandard reference is applicable to Xamarin, ASP.NET Core and the like.

### .NET Core 2.0

The recent .NET Core 2.0 is a milestone release for .NET going forward and for backwards compatibility. .NET Core is now at almost feature parity with the .NET Framework - there are only about 43 APIs that aren't supported. Here are some major API pieces that were missing in .NET Core 1.X that are now back in 2.0 - the reasons to not upgrade to .NET Core 2.0 are getting slimmer.

![](https://i.imgur.com/5VZW8bN.png)

With .NET Core 2.0 & .NET Standard 2.0, there's also little need to worry about legacy code. There are several attributes to .NET Core that make it well suited for transitioning from legacy code. Because .NET Standard 2.0 is at near API parity with .NET Framework 4.6.1, most applications can make use of code they already have. In addition, .NET Core includes a compatibility shim that allows projects to reference existing .NET Framework NuGet packages and projects. This means most packages on NuGet today are already compatible with .NET Core 2.x without the need to be recompiled. Having the ability to migrate existing applications to the next generation .NET, gives developers the freedom to write future proof code and move the business forward with minimal risk.

## XAML Standard

[XAML](https://en.wikipedia.org/wiki/Extensible_Application_Markup_Language) at its core, is just a simple XML-based markup language. There was no hardcore syntax specifications and no one team at Microsoft really owned XAML. As a result, as more app platforms picked up XAML as the UI layer, XAML itself got a little morphed each time. After all, it was up to the app platform's rendering engine to make sense of the XAML markup – so each one went a little in their own direction for maximum benefit.

All this brings us to today – a fragmented XAML world. WPF, Silverlight, UWP and Xamarin.Forms all talk a slightly different dialect of XAML. Developers still love XAML and the core concepts along with tooling remain about the same – there are just those nagging differences in XAML markup across platforms.

Consider the two most modern app platforms that use XAML – UWP and Xamarin.Forms. To do the exact same UI renderings, developers need to use different XAML markup, as illustrated in the handful of examples below:

* Placeholder control: `StackLayout` vs `StackPanel`?
* Text field control: `Label` vs `TextBlock`?
* Text entry control: `Entry` vs `TextBox`?
* `Button` control name: `Text` vs `Content`?
* `ForeColor` property: `TextColor` vs `ForeGround`?

This XAML fragmentation impedes code portability and is just frustrating for developers – clearly we can do better.

[XAML Standard](https://github.com/Microsoft/xaml-standard) is a standards-based effort to unify XAML dialects across app platforms. The goal is to specify a standard XAML vocabulary and all supporting app platforms adhere to the standard – apps should be able to share common XAML-based UI definitions.

These are still early days for XAML Standard. The XAML Standard specification is being developed out in the open with collaboration from the developer community. Post-specification, the immediate plan is to support the UWP and Xamarin.Forms platforms. Developers can continue developing UWP/Xamarin.Forms apps as they do today. When XAML Standard support is enabled, the XAML markup will just be reusable and shared between the frameworks.

Ever since the Microsoft Xamarin acquisition, hardcore XAML fans have been hoping for a dialect of XAML that lets them target all app platforms – not just Windows, but iOS and Android as well. The dream has been to re-define the Universal in UWP to include non-Microsoft platforms as well. XAML Standard is definitely a step in the right direction.

It should be noted that XAML Standard is a UI markup specification. Under the covers, it will use the native UI rendering mechanism of the supporting app platform, thus not holding back the developer or platforms in any way. Architecturally, you can see where the new XAML Standard, along with .NET Standard specifications, fit in the Microsoft development stack – it is critical to the true cross-platform portability story.

![](https://i.imgur.com/oGlVtyd.jpg)

For XAML Standard V1, the goal is to come up with a list of commonly used UI components and standardize their usage through specified properties/methods/events. The point is, no matter what platform you are writing apps for, you will set up the UI consistently using the same XAML syntax. Here's the list of some of the popular UI controls that are being standardized for properties and events:

* `Button`
* `TextBlock`
* `TextBox`
* `ComboBox`
* `Grid`
* `StackPanel`
* `Page`
* `UserControl`

Based on the type of control, developers will have standard ways of setting the content inside the UI component. Controls like `Button`, `TextBlock`, `TextBox`, and `ComboBox` deal with textual content and often need developer control over how the text is rendered. These controls will sport the following standard properties around managing Font:

* `FontSize`
* `FontWeight`
* `FontStyle`
* `FontFamily`

Developers often need to control the size and placement of common UI controls. To further aid standardization, the following properties will be available on all the UI controls listed above – just style them consistently:

* `Margin`
* `HorizontalAlignment`
* `VerticalAlignment`
* `Height`
* `Width`

Aside from app developers not having to remember multiple dialects of XAML for different platforms, the XAML Standards spec has one huge potential – portability. How often do you have a piece of UI that is very similar between the same app on various platforms? Think a simple user settings screen or a credit card payment screen – wouldn't it be nice if the UI could be shared?

Sharing of UI across platforms is exactly what XAML Standard enables. Bundle up some commonly used piece of UI using the standardized controls into a single XAML page – the syntax is the same for all supported platforms. All of a sudden, your XAML page just becomes shareable – take it to any platform and use it as is without modification. Imagine the kind of reusability this will bring to your code bases supporting apps on different platforms - thanks to XAML Standard.

## Better Web Apps with ASP.NET Core

Also fresh off the press is ASP.NET Core 2.0 - with full support for .NET Core 2.0 and a lots of tooling enhancements. ASP.NET Core 2.X provides .NET developers all of the tooling and framework features needed to build modern rich web applications. Here are some things to get excited about with ASP.NET Core 2.0:

* One of the fastest full-featured Web frameworks - just check the TechEmpower benchmarks
* Full support for .NET Core 2.0 and .NET Standard 2.0
* Backward compatibility to run on .NET Framework 4.6.1
* Combined MVC and Web API stack
* Can act as super fast API backend for Mobile apps
* New Razor Pages support
* New project templates
* Streamlined support for client-side JavaScript SPA frameworks
* Improved Logging, App Insight & Azure tooling

### CLI or Visual Tooling 

Developers building web apps with ASP.NET Core 2.0 have a plethora of rich tooling to choose from - come as you are and choose your development tools. Here are your choices:

* [Visual Studio 2017](https://www.visualstudio.com/vs/) (15.3+): a fully-featured IDE, featuring templates and extensions that target ASP.NET Core 2.0
* [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac):  a native macOS IDE with templates for ASP.NET Core 2.0
* [Visual Studio Code with the C# extension](https://code.visualstudio.com/docs/other/dotnet): a lightweight cross-platform text editor; provides a familiar coding experience and integrated terminal
* Command line tools: truly cross-platform; has all ASP.NET Core 2.0 templates and supports every stage of web app development
* A code text editor with code IntelliSense support through [OmniSharp](http://www.omnisharp.net)

The good news for developers is .NET tooling is consistent - no matter what be your development tooling. What CLI can do over commands is exactly what Visual Studio does visually. Take a look at some of the app templates supported by 'dotnet new' CLI tooling - you'll see corresponding similar templates on doing File | New in Visual Studio. Some of the app templates are what you expect from ASP.NET - some are unexpected; we'll break things down.

![](https://i.imgur.com/zvvGxGS.png)

![](https://i.imgur.com/lYMB1xp.png)

### Easy Dependencies

The ASP.NET team has created one of the most streamlined ASP.NET application architectures yet. With ASP.NET Core 2.0, application dependencies are bundled into a single metapackage reference - Microsoft.AspNetCore.All. Each dependency in the metapackage can be referenced individually, however using the bundled approach offers additional benefits. All the features of ASP.NET Core 2.x and Entity Framework Core 2.x are included in the bundled Microsoft.AspNetCore.All package. In addition, applications using the Microsoft.AspNetCore.All metapackage automatically take advantage of the .NET Core Runtime Store. The Runtime Store contains all the runtime assets needed for the application, thus reducing overheads during build/deployments.

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.All" Version="2.0.0" />
</ItemGroup>
```

### Easy Portability

One of the nicest things about .NET Core 2.0 and ASP.NET Core 2.0 for developers is portability - the framework and tooling is consistent across all platforms. Developers' choice of development OS does not matter - Windows and Mac have an identical experience. Gone is the ASP.NET specific Project.json file for dependencies and configuration - the familiar .CSProj file is back, as shown below for a boilerplate ASP.NET Core 2.0 project. Whether the ASP.NET project is scaffolded from Visual Studio File | New Project or through the dotnet new CLI tools, the resulting project has the same exact .CSProj file - it simply points to the target runtime framework and pulls in the .NET dependencies. This also means that developers can collaborate easier and have ASP.NET projects be portable across machines. It is perfectly conceivable to have multiple developers work on the same ASP.NET project, but using different IDEs - one on Visual Studio on Windows, one on Visual Studio for Mac and yet others, on simple text editors. The .SLN and .CSProj files are perfectly portable and the code writing experience is the same everywhere.  

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.All" Version="2.0.0" />
  </ItemGroup>
  <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.VisualStudio.Web.CodeGeneration.Tools" Version="2.0.0" />
  </ItemGroup>
</Project>
```

### Easy Bootstrapping

ASP.NET Core 2.0 web apps support fast streamlined bootstrapping - this is especially true for setup and initialization routines. The granular details of creating the webhost for the app, have been abstracted into the default CreateDefaultBuilder method. Developers retain the flexibility to use the default or create a custom webhost from scratch as needed.

```c#
public static IWebHost BuildWebHost(string[] args) =>
  WebHost.CreateDefaultBuilder(args)
         .UseStartup<Startup>()
         .Build();
```

Before ASP.NET Core 2.0, Razor view files were published as .CSHTML files, which were compiled at runtime -  this just-in-time compilation came at the expense of a performance hit. In older applications, developers could choose to manually precompile Razor views to reduce the published bundle and increase startup time. Now with ASP.NET Core 2.0 project templates, precompilation is enabled by default - this boosting app startup performance.

### Razor Pages

There is a new programming model for simple web pages in ASP.NET Core - called Razor Pages. Sometimes, you just want to display some content on a page, without going through much ceremony and may be do a page postback to server - this is exactly what Razor Pages is meant for. Here are few more pointers about Razor Pages to clear the air of mystery:

* New feature baked into ASP.NET Core MVC
* Auto-enabled for simple page-focused scenarios
* Simple convention-based routing | Razor Pages are served up from Pages directory
* A simple page-level Directive turns Pages into MVC Actions | They handle requests directly
* Razor Pages skip the Controller orchestration | Sort of a simplified Model-View pattern
* Razor Pages are CSHTML Views with optional Code-behind files
* Razor Pages fully support Razor syntax, TagHelpers and MVC validations 
* The PageModel contains Handlers to support HTTP verbs
* Razor Pages are not to be confused with WebForms | There is no ViewState between client/server

Here is what ASP.NET Core 2.0 project templates put out for a Razor Pages project - notice the simplicity of the Pages directory, as compared to a full MVC project:

![](https://i.imgur.com/7QeWuFO.png)

Let's look at a simple Razor Page view - a CSHTML file with a @page directive on top:

```ASP
@page

@model AboutModel
@{
  ViewData["Title"] = "About";
}

<h2>@ViewData["Title"]</h2>
<h3>@Model.CodeBehindModelMessage</h3>

<p>Use this area to provide additional information.</p>
```

Notice how the view points to a Model and pulls data out of the model. Turns out, the model is defined in a code-behind file - with the same name as the view with .CS at end, simply by convention:

```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc.RazorPages;

namespace AspNetCore2Razor.Pages
{
  public class AboutModel : PageModel
  {
    public string CodeBehindModelMessage { get; set; }

    public void OnGet()
    {
      CodeBehindModelMessage = "This is from the code-behind.";
    }
  }
}
```

Notice how the model implements a PageModel - a base class that binds together much of the Razor Pages features. The page models can define methods that correspond to HTTP verbs - like Get, Put, Delete and Post - for supporting CRUD operations when the Razor Page posts back to the server. You can see how this simple model helps support putting content out on Razor Pages and adding dynamic features through simple server roundtrips.

Now, here's a little variation to defining a PageModel for a Razor Page - this time in the View itself:

```ASP
@page
@model ContactModel
@using Microsoft.AspNetCore.Mvc.RazorPages

@functions {
  public class ContactModel : PageModel
  {
    public string InPageModelMessage { get; set; }

    public void OnGet()
    {
      InPageModelMessage = "This is from the View.";
    }
  }
}

<h3>@Model.InPageModelMessage</h3>

<address>
  One Microsoft Way<br />
  Redmond, WA 98052-6399<br />
  <abbr title="Phone">P:</abbr>
  425.555.0100
</address>

<address>
  <strong>Support:</strong> <a href="mailto:support@example.com">support@example.com</a><br />
  <strong>Marketing:</strong> <a href="mailto:marketing@example.com">marketing@example.com</a>
</address>
```

Notice how the PageModel and server-side C# code can be written entirely within a Razor Page view - skipping the code-behind file altogether. While doable, this is not suggested for any complicated pages with substantial code in the PageModel - separation of concerns is always nice. 

### SPA Templates

Traditional ASP.NET web development mostly relies on server-side rendering with Razor and other view engines. However, browsers have come a long way and JavaScript is ubiquitous - one may argue that client-side web development is where things are headed. ASP.NET Core 2.0 is a modern web framework and in no way, attempts to hold developers back in building their web apps however they see fit.

Developers have always been able to bring in JavaScript, CSS and other front-end web development artifacts into the ASP.NET stack. However modern full-featured JavaScript frameworks do a lot out of the box and it doesn't make much sense for developers to reinvent the wheel. There are several popular Single Page Application (SPA) type JavaScript frameworks that aid in building fully front-end web apps with navigation, state management, bundling and the works. Turns out, ASP.NET Core 2.0 works very nicely with these SPA frameworks.

Arguably, two of the most popular JavaScript SPA frameworks are - Angular and React. And ASP.NET Core 2.0 offers built-in templates - both with dotnet CLI or the Visual Studio File | New Project route. If going the Angular route, below is a sample project as scaffolded by the ASP.NET Core 2.0 Angular template:

![](https://i.imgur.com/Yk3ICXj.png)

Developers should notice a few differences right away, compared to traditional ASP.NET MVC projects:

* The Model and View folders aren't there | The Controllers do bare minimum
* The point is to build a true SPA | All of the app's functionality is client-side
* Accordingly, the ClientApp folder is where most of the app's code lives
* App features are built as reusable app components
* npm is used to bring in app dependencies
* WebPack is used for configurations and component bundling
* Each component is commonly made up of HTML and CSS | JavaScript pulls it all together
* App business logic is commonly written in TypeScript for Angular 2.0 forward

Below is a sample app component in TypeScript:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})

export class AppComponent { }
```

Once the ASP.NET Core 2.0 Angular template is done scaffolding, developers have a familiar dotnet run or F5 exoerience to run the app - notice the app template being different from traditional ASP.NET apps. The experience when using the ASP.NET Core 2.0 React template is identical.

![](https://i.imgur.com/MDSsMGW.png)

The Angular/React templates in ASP.NET Core 2.0 are meant get .NET developers to a good starting point with SPA projects and includes abstractions to fast-track newcomers. Like any other project templates, these new SPA templates aren't required, but rather helpful. Development teams can always build two separate projects - a fully front-end SPA web app with JavaScript frameworks and an ASP.NET WebAPI project serving up data from the backend. ASP.NET is quite happy in this role and will support APIs for a variety of client apps. But most modern SPA/JavaScript web apps need a lot of orchestration - configuring services, bundlers and managing dependencies. This wild-west approach may be intimidating for many .NET developers and this is where the ASP.NET Core 2.0 Angular/React templates comes in - they have pre-configured front-end tooling and hook up a bunch of things for developers behind the scenes.

Here's a handful of benefits that come with the SPA templates in ASP.NET Core 2.0:

* Support for server-side pre-rendering of JavaScript components | Embeds NodeJS in ASP.NET runtime hosting
* Webpack Hot Module Replacement | Speeds up dev/test cycles by automatically refreshing components on TypeScript/JavaScript/CSS edits
* Node Module dependency management | All of what Angular/React need are referenced and managed
* Webpack integration is built-in | Does bundling, minification and TypeScript compilation

### Telerik UI for Web

As you can see, modern ASP.NET comes in variety of flavors - developers can mix/match server side C# with client-side JavaScript. One thing stays true though - web apps need polished UI to stand out and developers should not reinvent the wheel. Telerik offers various UI suites for lighting up your web apps, no matter how you build them: 

* [Telerik UI for ASP.NET AJAX](https://telerik.com/aspnet-ajax) - for WebForms apps
* [Telerik UI for ASP.NET MVC](https://telerik.com/aspnet-mvc) - for traditional MVC web apps
* [Telerik UI for ASP.NET Core](https://telerik.com/aspnet-core-ui) - support for ASP.NET Core and TagHelpers
* [Kendo UI for jQuery](https://telerik.com/kendo-ui) - UI widgets for jQuery-based web apps
* [Kendo UI for Angular](https://telerik.com/kendo-angular-ui) - UI components for Angular-based web apps
* [Kendo UI for React](https://telerik.com/kendo-react-ui) - UI components for React-based web apps
* [Kendo UI for Vue](https://telerik.com/kendo-vue-ui) - UI components for Vue-based web apps

## Better Mobile Apps with Xamarin

Congratulations! You have picked Xamarin to build your next cross-platform mobile app. You get to reuse your existing skills in C#/XAML and build a truly native cross-platform app from a single code base. For .NET developers, Xamarin has almost single-handedly democratized cross-platform development - you can target apps running on just about every platform and every device.

All Xamarin apps - Xamarin.iOS/Android and Xamarin.Forms work with .NET Standard libraries. Xamarin developers should look to abstract out any code that be shared - and this is best done as a .NET Standard library for maximum portability. The dream of re-using code between Xamarin and other .NET apps is a reality - thanks to the common API platform offered by .NET Standard. Needless to say, .NET Standard libraries can be created from scratch in Visual Studio, Visual Studio for Mac or CLI:

![](https://i.imgur.com/946nMYC.png)

![](https://i.imgur.com/Gihrkn2.png)

Any .NET Standard library can be consumed inside Xamarin apps - be it directly from NuGet or through 3rd party sources. Developers can use .NET Standard dependencies in their Xamarin apps out of the box - no changes to existing dependencies required. In fact, the recent Xamarin.Forms 2.4.0 stable release has full support for .NET Standard 2.0. Good times ahead for Xamarin developers trying to share code across platforms.

### Telerik UI for Xamarin

You are completely sold on the Xamarin promise. You have grabbed the IDE/tools of your choice, started building your dream Xamarin app and incorporated the necessary frameworks. Guess what? Your end users do not see any of magic behind the scenes. What they do see is the app UI and the fluidity of user experience that your app provides. You can try reinventing the wheel on complex UI or go for some well-engineered UI controls out of the box. Sure there are a few offerings, but let's talk about what is arguably the most polished and developer-friendly.

Telerik UI for Xamarin includes elegant, polished and performant native UI widgets for all your Xamarin apps. With UI for Xamarin, you'll get to deliver your Xamarin apps quicker and delight users with beautiful functional UI.

It is easy to integrate Telerik UI for Xamarin in your existing projects - get the NuGet package for Visual Studio on Windows/Mac or just download the bits. If you have the luxury of starting greenfield projects, Telerik UI for Xamarin provides some simple Visual Studio Templates to get you to a good starting point - again both on Windows or Mac. 

So what do you get with UI for Xamarin? Beautiful professionally engineered and highly performant UI - all the ammunition you need to delight users. You have gorgeous Charts, must-have ListViews, LOB-friendly DataGrids, handy Gauges, pixel-perfect Calendars, magical SideDrawers, super-helpful DataForm, essential TabView and much more. Powering Telerik UI for Xamarin is truly native UI for each platform - with support for Xamarin.iOS, Xamarin.Android and Xamarin.Forms. 

![](https://i.imgur.com/g6hoUHh.png)

![](https://i.imgur.com/NafDb2N.png)

![](https://i.imgur.com/MVFJfME.png)

![](https://i.imgur.com/gVV2Alk.png)

![](https://i.imgur.com/2wJ6iFo.png)

![](https://i.imgur.com/kDcrW2g.png)

![](https://i.imgur.com/qlQht3B.png)

![](https://i.imgur.com/Z6GhWu7.png)

![](https://i.imgur.com/jb7aKLM.png)

![](https://i.imgur.com/fRY6mkt.png)

## Better Windows Apps with UWP

Over the past decade, Windows has undergone many changes to support industry trends and reflect Microsoft's vision for its flagship operating system. Numerous features and improvements were added over the years with Windows 7 and Windows 8. However, it wasn't until Windows 10 that things became interesting.

Windows 10 represents a significant milestone for Windows as a platform for both users and developers. Unlike previous versions of Windows, Windows 10 is not confined to the desktop. Instead, it runs across a wide range of devices and form factors. This includes IoT devices (running on ARM or x86/x64 architectures) and platforms like the Xbox, HoloLens, and Surface Hub. For developers, Windows 10 also introduces a new way for creating apps called the [Universal Windows Platform](https://docs.microsoft.com/en-au/windows/uwp/get-started/universal-application-platform-guide) (UWP).

UWP represents an exciting opportunity as it allows developers to target a rich ecosystem of Windows-based devices through a unified API. It achieves a long-standing goal at Microsoft of having one -- and only one -- version of Windows to target. Through this unified API, developers can now build applications that can run across devices.

![](https://i.imgur.com/l9c7npS.png)

Not all devices are the same. Some support capabilities that are unique. UWP supports the ability to target these capabilities through Extension SDKs. These are device-specific APIs that can be targeted by developers to take advantage of these features.

In addition to leveraging device-specific APIs, UWP also enables developers to build applications with adaptive controls and input. This is a concept known as Responsive Design that's being populated in web development circles. This is the ability for applications to work across devices with differing screen dimensions and forms of user input (i.e. Xbox One controllers).

### Windows Store

One of the biggest changes introduced with Windows 8 and featured prominently in Windows 10 is the Windows Store. This is Microsoft's distribution platform for free and commercial apps. It's a curated environment that requires developers to have their applications certified prior to publication. This may seem like a significant hurdle, but one that's worthwhile when you consider the fact that it makes these applications available to millions of Windows users.

![](https://i.imgur.com/wExvfzZ.png)

The Windows Store uses the .AppX packaging format, which is a step up from the traditional model of executables and libraries. The .AppX packaging format allows developer to express their application's intent. This enables them to express which capabilities they require for applications to operate correctly on Windows 10. This way, users can download applications from the Windows Store with a higher level of trust over the traditional application model.

### Telerik UI for UWP

Telerik UI for UWP is a suite of 20+ UI controls that help developers build UWP applications. It contains controls that address common UI requirements in line-of-business (LOB) applications, including data management (DataForm), scheduling (Calendar), navigation (RadialMenu), data visualization (Chart), and more.

![](https://i.imgur.com/kkDpH5S.png)

This controls can be easily incorporated into existing UWP projects via NuGet. Once added, controls can be added and qualified in XAML pages through prefixes and namespaces. Here's an example using the `RadialGauge` control:

```xaml
<Page xmlns:telerik="using:Telerik.UI.Xaml.Controls.DataVisualization">
  ...
  <telerik:RadRadialGauge>
    ...
  </telerik:RadRadialGauge>
</Page>
```

These controls can be used with controls from other libraries such as the UWP Community Toolkit. This combination empowers developers to build extremely powerful and versatile UWP applications. Incorporating these controls into existing applications is fairly trivial. That stated, if developers looking for a guided approach towards building new applications with Telerik UI for UWP should check out Windows Template Studio:

![](https://i.imgur.com/YE41SyD.png)

This extension for Visual Studio will generate a UWP application through templates. The goal is to get you up and running quickly with a project structure and source files that can be modified afterward.

Recently, Windows Template Studio added templates for the Chart and Grid controls from Telerik UI for UWP:

![](https://i.imgur.com/iC7SCXg.png)

Selecting either of those controls will generate pages will the necessary XAML and code needed to display them:

![](https://i.imgur.com/hnxbXfn.png)

![](https://i.imgur.com/5STFP47.png)

Windows Template Studio is available to [download and install from the Visual Studio Marketplace](https://aka.ms/wtsinstall).

## Conclusion

PS: Many images courtesy of Microsoft.
