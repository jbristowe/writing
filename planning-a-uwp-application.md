# Planning a UWP Application

The [Universal Windows Platform][1] (UWP) offers an exciting opportunity for developers to target a rich ecosystem of Windows-based devices through a unified API. This whitepaper will help you plan the development of a UWP application by documenting the libraries, frameworks, and tools that are available to developers.

## Why UWP?

UWP provides the best platform to developers targeting its 400+ million Windows 10 users. It enables developers to build applications that can leverage modern experiences through devices that extend beyond the PC, such as the Xbox and HoloLens.

![](https://i.imgur.com/JWQXJL6.png)

In addition to these devices, UWP applications can leverage a rich programmatic interfaces through .NET, Win32, and UWP APIs. This platform is facilitated through the Microsoft Store and the Microsoft Store for Business.

UWP is a compelling because it provides a platform of new or improved capabilities. It enables developers to build modern user experiences through an adaptive interfaces. This is coupled with a rich set of APIs that support natural user inputs such as touch and ink. It unlocks the potential to reach new audiences by providing the ability to target a variety of devices, including the Surface Hub and HoloLens. It provides much improved servicing experience for applications through its modern installer. Applications are now deployed to Windows 10 as Windows App packages (AppX). These are self-describing in terms of permissions and capabilities. These packages are provided through the curated experience of the Microsoft Store (or private alternatives).

## Migrating Existing Applications to UWP

When planning a UWP application, you don't need to start from scratch. Indeed, a wide variety of approaches exist. You can preserve the investments you've made into technologies like Win32, Windows Forms (WinForms), or the Windows Presentation Foundation (WPF) by migrating your application over to UWP. Technologies such the [Desktop Bridge][4] enable you to distribute applications built with technologies like these as Windows App packages. Not only do you gain the benefits of an improved servicing model, you can also extend out its capabilities through UWP features like a XAML-based UI, background tasks, and more.

### Desktop Bridge

The Desktop Bridge represents a great opportunity for developers wanting to leverage UWP in existing applcations and make them available through the Store or the Store for Business. It's infrastructure that's built into UWP that enables applications built with Win32, Windows Forms, or WPF.

Microsoft has [published a list of things to know before you package your application and use the Desktop Bridge](https://docs.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-prepare).

### Desktop App Converter

Microsoft provides a number of tools to help you migrate your existing applications to UWP. The [Desktop App Converter](https://aka.ms/converter) (DAC) is a command-line tool available through the Microsoft Store that will package your application into a Windows app package. The DAC can also build Windows app packages based on applications that have an installer (i.e. foo.msi). Despite its name, the DAC doesn't "convert" your application during this process. In fact, it remains unchanged.

## Devices

For a list of compatible barcode scanners, see [Supported Point of Service Peripherals](https://docs.microsoft.com/windows/uwp/devices-sensors/pos-device-support). 

## Accessibility

### Accessbility Testing Tools in the Windows SDK

The [Windows Software Development Kit][2] (SDK) provides a number of excellent tools that can be used to test the accessibility of UWP applications.

#### Accessible Event Watcher (AccEvent)

This tool can be used to track the events raised by UI elements within an application.

![](https://i.imgur.com/4hQ4k7U.png)

#### UI Accessibility Checker (AccChecker)

A tool that verifies that key UI accessibility requirements are met in the design and implementation of UI Automation (UIA) or Microsoft Active Accessibility (MSAA) regardless of the underlying UI framework.

![](https://i.imgur.com/8RXQYNx.png)

#### Inspect Object (Inspect.exe)

A tool that allows you to select any UI element and view its accessibility data.

#### UI Automation Verify

![](https://i.imgur.com/5sgm71l.png)

Testing framework for manual and automated testing the implementation of Microsoft UI Automation by a control or application.

## UWP Application Development Requirements

UWP application development is best suited for a system running the latest versions of Windows and Visual Studio. Namely, Windows 10 and Visual Studio 2017. While earlier versions of Windows and Visual Studio can be used, their ability to run, debug, and/or test UWP applications can be quite limited.

In addition to the software requirements for UWP application development, it is important to consider the hardware requirements as well. These can vary depending on the device families (i.e. HoloLens, IoT, Xbox) you wish to target. As a general rule, it's best to test UWP applications on real devices. However, Visual Studio provides excellent tools for emulating environments if these devices are unavailable.

When building UWP applications, it's important to enable Developer Mode on the development machine you're targeting along with any devices you plan to deploy your application. This feature allows you to sideload applications to your machine and run applications in debug mode through Visual Studio.

![](https://i.imgur.com/8INk4CV.png)

Developers running on macOS can build applications for UWP in virtualised environments like [Oracle VirtualBox](https://www.virtualbox.org/), [VMware Fusion](https://www.vmware.com/products/fusion.html), and [Parallels Desktop](https://www.parallels.com/products/desktop/). Apple Boot Camp is a suitable alternative as well.

### Windows Device Portal

The Windows Device Portal (WDP) is a new feature that' s available to developers on each device family. In addition to providing the ability to remote manage a device, it also provides a set of diagnostic tools to aid UWP application development.

![](https://i.imgur.com/fhwspXw.png)

The Windows Device Portal differs from other diagnostic tools available through SDKs in that it's available through a web interface. It is also available to each device family: HoloLens, IoT, Xbox, Desktop, and Phone. Each configuration provides a standard set of tools for tasks like managing apps and monitoring system performance.

The Windows Device Portal is enabled through your device settings. When enabled, the Windows Device Portal is accessible through your machine's IP address (or hostname) and an assigned port number.

![](https://i.imgur.com/OWWfusI.png)

#### Device Portal for Desktop

The [Device Portal for Desktop](https://docs.microsoft.com/en-us/windows/uwp/debug-test-perf/device-portal) is a feature available in Windows 10 that provides centralised access to diagnostic tools that assist in UWP development that targets the Windows desktop.

![](https://i.imgur.com/5hdursp.png)

The Device Portal for Desktop provides a number of diagnostic tools that are particularly useful for UWP development. For example, you can manage packaged applications as well as view and manipulate files stored by your sideloaded apps. Features such as the ability to [debug UWP app streaming install](https://blogs.msdn.microsoft.com/appinstaller/2017/08/09/using-windows-device-portal-to-debug-streaming-install/) and simulating your device location were added to the Device Portal for Desktop in the Fall Creators Update.

## Building Adaptive UWP Applications

Developers should consider supporting the following classifications of adaptive UWP applications during development:

1. Responsive user interface
2. Version adaptive
3. Platform adaptive

### Responsive User Interface

Since UWP applications have the ability to operate across a range of device families, it is important to consider the manner in which a UWP application will behave across various resolutions of displays. Fortunately, a responsive user interface is supported through facilities available to UWP applications through languages like XAML and tools like Visual Studio 2017.

UWP supports the concept of a VisualStateManager that allows applications to respond to changes in its appearance. These changes can be triggered when running an the application on devices from small screens to large screens or no screens at all. Tools like Visual Studio 2017 complement this capability by providing the ability to preview how an application will look on a range of device families at design-time.

### Version Adaptive

UWP applications are said to be version adaptive if they are built with the capability of supporting multiple versions of Windows 10. This means that these applications are able to operate normally on a minimum version of the APIs that are available through a particular version of Windows 10. It also means that these applications can incorporate features added to APIs from later versions of Windows 10. Both of these abilities are facilitated through the configuration of a UWP project in Visual Studio as well as version adaptive code and conditional XAML.

### Platform Adaptive

UWP applications are said to be platform adaptive if they are built to incorporate features for each device family it supports.

## UI Libraries

UI libraries save developers time by providing pre-built controls that can be incorporated into applications. There are many open source and commercial UI libraries available for developers building UWP applications.

### UWP Community Toolkit

The [UWP Community Toolkit](https://github.com/Microsoft/UWPCommunityToolkit) provides a set of developer tools, code helpers, UI controls, application services, and notifications for UWP developers. It serves as collaboration between Microsoft and the UWP developer community and it is available as an open source project on GitHub.

![](https://i.imgur.com/folHRrK.png)

### Telerik UI for UWP

[Telerik UI for UWP][3] is an open source project on GitHub that provides 20+ UI controls for data management, layout, scheduling, editors, navigation, data visualisation, and interactivity.

![](https://i.imgur.com/YRDboei.png)

### ReactiveUI

[ReactiveUI](https://github.com/reactiveui/ReactiveUI) provides a composable and functional reactive model-view-viewmodel framework for .NET (including UWP).

![](https://i.imgur.com/e0DMQJ6.png)

### UICompositionAnimations

[UICompositionAnimations](https://github.com/Sergio0694/UICompositionAnimations) exposes classes and APIs to quickly implement animations and effects to a UWP application. It also has a collection of helper methods to load Win2D images, dispatch code to the UI thread and more.

### Template 10

[Template 10](https://github.com/Windows-XAML/Template10) is a set of Visual Studio project templates for common patterns in UWP applications. It is similar to the [UWP Community Toolkit](https://github.com/Microsoft/UWPCommunityToolkit) in that it provides a set of controls, behaviours, services, converters, and more.

### Caliburn.Micro

[Caliburn.Micro](http://caliburnmicro.com/) ([GitHub](https://github.com/Caliburn-Micro/Caliburn.Micro))

### Prism

### OxyPlot

[OxyPlot](http://www.oxyplot.org/)

### LiveCharts

[LiveCharts](https://github.com/beto-rodriguez/Live-Charts) provides simple, flexible, interactive & powerful charts, maps and gauges for .NET.

## .NET Core

* .NET Core vs Portable Class Libraries (PCLs)

## Tools

### Windows Template Studio

[Windows Template Studio](https://aka.ms/wtsinstall) is an extension for Visual Studio 2017 that will generate a UWP application through templates. It's a useful tool to  get you up and running quickly with a project structure and source files that can be modified afterward.

![](https://i.imgur.com/YE41SyD.png)

Windows Template Studio will generate UWP applications based upon the attribute sets you specify. These attribute sets determine the various characteristics of the application such as its UI navigation style, supporting frameworks, application pages, and Windows 10 features.

## Automated Deployments of UWP Applications

Automated deployment and the build management tasks that are associated with this process serve the role of automating the process of generating builds, deploying to test machines, and executing tests. They are a crucial aspect of having an efficient development process. When it comes to UWP application development, there are a number of solutions are available to manage builds and automate their associated tasks.

### VSTS
### Octopus Deploy

## Notes

* [MahApps.Metro.IconPacks]() ([GitHub](https://github.com/MahApps/MahApps.Metro.IconPacks))

[1]: https://en.wikipedia.org/wiki/Universal_Windows_Platform
[2]: https://en.wikipedia.org/wiki/Microsoft_Windows_SDK
[3]: https://www.telerik.com/universal-windows-platform-ui
[4]: https://developer.microsoft.com/en-us/windows/bridges/desktop
