# Planning a UWP Application

The [Universal Windows Platform][1] (UWP) offers an exciting opportunity for developers to target a rich ecosystem of Windows-based devices through a unified API. This whitepaper will help you plan the development of a UWP application by documenting the libraries, frameworks, and tools that are available to developers.

## Why UWP?

UWP provides the best platform to developers targeting its 400+ million Windows 10 users. It enables developers to build applications that can leverage modern experiences through devices that extend beyond the PC, such as the Xbox and HoloLens.

![](https://i.imgur.com/JWQXJL6.png)

UWP enables developers to target a core API that provides a consistent development experience across devices. Recently, the tooling for UWP now supports .NET Standard 2.0, a specification of APIs for .NET implementations. Extension SDKs are also available for each device family that a developer wishes to target. These are APIs that have been implemented for a particular device family.

UWP applications are made available through a trusted and curated experience of the [Microsoft Store][0]. Organizations can also choose to provide an internal channel for these applications through the Microsoft Store for Business and Microsoft Store for Education. The Microsoft Store provides an improved servicing model for users; applications are easily discoverable and kept up-to-date. It also provides a great distribution model for developers. Applications can be built, packaged, and made available to the 400+ million users of Windows 10 devices around the globe. Historical challenges like the handling of licensing and monetization is managed by this infrastructure. It also provides much improved servicing experience for applications through its modern installer. UWP applications are now deployed as Universal Windows Packages (AppX). This is the file format used for UWP applications that contains an application's assets and a description of its permissions/capabilities. This, coupled with the UWP app model, facilitates things like differential updates and clean uninstallation.

![](https://i.imgur.com/D7Wbxnb.png)

In addition to its wide range of device families, UWP provides a compelling opportunity for developers because it provides a platform of new and improved application capabilities. It enables them to build modern user experiences with an adaptive interfaces. This means that applications can be built with the optimal user experience in mind. This is coupled with a rich set of APIs that support natural user inputs such as touch and ink. It unlocks the potential to reach new audiences by providing the ability to target a variety of devices, including the Surface Hub and HoloLens.

## Migrating Existing Applications to UWP

When planning to build a UWP application, you don't need to start from scratch. Indeed, a wide variety of approaches exist. You can preserve the investments you've made into existing technologies like Win32, Windows Forms (WinForms), or the Windows Presentation Foundation (WPF) by migrating your application over to UWP. This can be accomplished through technologies such the [Desktop Bridge][4], which enables you to package your pre-existing applications as Windows App packages. This represents a great opportunity for developers wanting to leverage UWP and make these applications available through the Microsoft Store. Microsoft has [published a list of things to know before you package your application and use the Desktop Bridge](https://docs.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-prepare). Once packaged, these applications can be made available through the Microsoft Store. Not only do you gain the benefits of an improved servicing model (i.e. clean uninstallation), you can also modernize the application through UWP features like a XAML-based UI, live tiles, background tasks, and more.

![](https://i.imgur.com/K8KlAwH.png)

Microsoft provides a number of tools to help you migrate your existing applications to UWP. The [Desktop App Converter](https://aka.ms/converter) (DAC) is a command-line tool available through the Microsoft Store that will convert your application installer into a Windows app package. It accomplishes this by recording all system modifications made by your installer and creating a corresponding Universal Windows Package for your application. This is done independently of your application. That means you can create these packages for applications built with technologies like Visual Basic 6, WPF, and [Electron](https://electron.atom.io/). Once you've converted your installer, you can enhance your existing application by leveraging UWP APIs or adding new resources to the Universal Windows Package. From there, you can migrate parts of your existing application to UWP to take advantage of modern features like a XAML-based UI or ink support. Over time, you can migrate your code fully to UWP to reach Windows 10 devices like the HoloLens and Xbox.

## UWP Application Development Requirements

UWP application development is best suited for a system running the latest versions of Windows and Visual Studio. Namely, Windows 10 and Visual Studio 2017. While earlier versions of Windows and Visual Studio can be used, their ability to run, debug, and/or test UWP applications can be quite limited.

In addition to the software requirements for UWP application development, it is important to consider the hardware requirements as well. These can vary depending on the device families (i.e. HoloLens, IoT, Xbox) you wish to target. As a general rule, it's best to test UWP applications on real devices. However, Visual Studio provides excellent tools for emulating environments if these devices are unavailable.

When building UWP applications, it's important to enable Developer Mode on the development machine you're targeting along with any devices you plan to deploy your application. This feature allows you to sideload applications to your machine and run applications in debug mode through Visual Studio.

![](https://i.imgur.com/8INk4CV.png)

Developers running on macOS can build applications for UWP in virtualised environments like [Oracle VirtualBox](https://www.virtualbox.org/), [VMware Fusion](https://www.vmware.com/products/fusion.html), and [Parallels Desktop](https://www.parallels.com/products/desktop/). Apple Boot Camp is a suitable alternative as well.

## Interactions and Devices

Microsoft has made a considerable effort to document the kinds of interactions and devices you can target when building UWP applications. User interactions are those that incorporate actions from connected peripherals that extend beyond the keyboard and mouse. These include pen, touch, speech, gesture, and so on. They also cover specific devices like the Surface Dial, which is supported in UWP. User interactions and devices are important to consider when planning your UWP application. That's because UWP scans a large range of device families with differing forms of user control. Take, for example, the HoloLens. This is a device that has a unique set of gestures that are coupled with a user interface that augments the user's reality. In this scenario, UWP provides support through speech commands, gestures, and input from an on-screen keyboard.

It's important to consider the device families you wish to target when planning a UWP application. Windows 10 covers a wide range of devices, each with its own capabilities and constraints. These characteristics are particularly important when designing the user experience (see "Building Adaptive UWP Applications" for more information). For other scenarios, UWP provides integration with a wide range of input devices. For example, see [Supported Point of Service Peripherals](https://docs.microsoft.com/windows/uwp/devices-sensors/pos-device-support) for list of compatible barcode scanners.

Tools like Visual Studio provide an integrated debugging experience that allows you to be effective when targeting devices. This is complemented by the Windows Device Portal to help developers during the development process.

### Windows Device Portal

The Windows Device Portal (WDP) is a new feature that's available to developers on each device family. In addition to providing the ability to remote manage a device, it also provides a set of diagnostic tools to aid UWP application development.

![](https://i.imgur.com/fhwspXw.png)

The Windows Device Portal differs from other diagnostic tools available through SDKs in that it's available through a web interface. It is also available to each device family: HoloLens, IoT, Xbox, Desktop, and Phone. Each configuration provides a standard set of tools for tasks like managing apps and monitoring system performance.

The Windows Device Portal is enabled through your device settings. When enabled, the Windows Device Portal is accessible through your machine's IP address (or hostname) and an assigned port number.

![](https://i.imgur.com/OWWfusI.png)

#### Device Portal for Desktop

The [Device Portal for Desktop](https://docs.microsoft.com/en-us/windows/uwp/debug-test-perf/device-portal) is a feature available in Windows 10 that provides centralised access to diagnostic tools that assist in UWP development that targets the Windows desktop.

![](https://i.imgur.com/5hdursp.png)

The Device Portal for Desktop provides a number of diagnostic tools that are particularly useful for UWP development. For example, you can manage packaged applications as well as view and manipulate files stored by your sideloaded apps. Features such as the ability to [debug UWP app streaming install](https://blogs.msdn.microsoft.com/appinstaller/2017/08/09/using-windows-device-portal-to-debug-streaming-install/) and simulating your device location were added to the Device Portal for Desktop in the Fall Creators Update.

## Building Adaptive UWP Applications

When planning a UWP application, it's important for developers consider building UWP applications that adapt to the device family they run on. To be adaptive, developers should design for the user interface that will render across a wide range of screens. These screens can vary widely in terms of resolution, DPI density, and so on. Developers should also design for the version of Windows 10 that these applications are running on. As Windows 10 evolves, more and more capabilities are added. An adaptive application can incorporate version-specific features available from the underlying operating system and exposed through UWP APIs. This concept of being adaptive also applies to the platform that these UWP applications are running on. The good news is that developers can build UWP applications that detect the presence of these platforms and the APIs they expose. If they are present at run-time, the application can take advantage of them.

### Responsive User Interface

Since UWP applications have the ability to operate across a range of device families, it is important to consider the manner in which a UWP application will behave across various resolutions of displays. Fortunately, a responsive user interface is supported through facilities available to UWP applications through languages like XAML and tools like Visual Studio 2017.

UWP supports the concept of a VisualStateManager that allows applications to respond to changes in its appearance. These changes can be triggered when running an the application on devices from small screens to large screens or no screens at all. Tools like Visual Studio 2017 complement this capability by providing the ability to preview how an application will look on a range of device families at design-time.

Microsoft provides excellent tools for building the user interface of a UWP application. Visual Studio provides an integrated experience that allows you switch screen resolutions and observe how these changes impact your user interface.

![](https://i.imgur.com/7hIu9hN.png)

Another useful tool is [Adobe Experience Design][5] (XD). This is a tool you can use to design the user interface of mobile and desktop applications. Microsoft provides a design toolkit that allows you to incorporate core UWP controls.

![](https://i.imgur.com/kSaQxoK.png)

### Version Adaptive

UWP applications are version-adaptive if they are built with the capability of supporting multiple versions of Windows 10. This means that these applications are able to operate normally on a minimum version of the APIs that are available through a particular version of Windows 10. It also means that these applications can incorporate features added to APIs from later versions of Windows 10. Both of these abilities are facilitated through the configuration of a UWP project in Visual Studio as well as version adaptive code and conditional XAML.

### Platform Adaptive

UWP applications platform-adaptive if they are built to incorporate features for each device family it supports. These capabilities are exposed through extension SDKs that you can incorporate into your application project. It's important that developers test the presence of the APIs exposed by the platform before executing calls against them.

## Software management tools

To manage the development of a UWP project, software management tools are required to manage code, assets, and team members' tasks:

| Software management tools  | Examples |
|---|---|
|Issues and feature tracker  | TFS, GitHub  |
|Version control system  | TFS, GitHub  | 
|Document/asset storage  | Slack, internal network storage, Office 365 |
|Team communication|Slack, HipChat, IRC, Skype|
|Task manager| Visual Studio Team Services, GitHub Org Tasks, Trello|
|Continuous Integration and Continuous Delivery| Visual Studio Team Services, Azure|
 
It's important to ensure that developers adopt these tools. It's a vital part of frequently assessing and improving development workflows.

## UI Libraries and Tools

UI libraries save developers time by providing pre-built controls that can be incorporated into applications. There are many open source and commercial UI libraries available for developers building UWP applications.

### XAML Controls

There are many core controls available in UWP that developers can use to build applications. An effective way to experience them is through the XAML Controls Gallery application that's available on the Microsoft Store:

![](https://i.imgur.com/AvlXptX.png)

This application provides demos and code samples that you can incorporate into your project:

![](https://i.imgur.com/jaxzb7k.png)

### UWP Community Toolkit

The [UWP Community Toolkit](https://github.com/Microsoft/UWPCommunityToolkit) provides a set of developer tools, code helpers, UI controls, application services, and notifications for UWP developers. It serves as collaboration between Microsoft and the UWP developer community and it is available as an open source project on GitHub.

![](https://i.imgur.com/Y6AUEzq.png)

The UWP Community Tookit application is incredibly useful because it allows you to manipulate properties on highlighted controls to see the impact of changes:

![](https://i.imgur.com/folHRrK.png)

### Telerik UI for UWP

[Telerik UI for UWP][3] is an open source project on GitHub that provides 20+ UI controls for data management, layout, scheduling, editors, navigation, data visualisation, and interactivity.

![](https://i.imgur.com/YRDboei.png)

These controls are easy to integrate into UWP applications through NuGet.

![](https://i.imgur.com/hnxbXfn.png)

Like the UWP Community Toolkit, the source code for these controls are available on GitHub: [Telerik UI for UWP](https://github.com/telerik/UI-For-UWP).

### Template 10

[Template 10](https://github.com/Windows-XAML/Template10) is a set of Visual Studio project templates for common patterns in UWP applications. It is similar to the [UWP Community Toolkit](https://github.com/Microsoft/UWPCommunityToolkit) in that it provides a set of controls, behaviours, services, converters, and more.

### Windows Template Studio

[Windows Template Studio](https://aka.ms/wtsinstall) is an extension for Visual Studio 2017 that will generate a UWP application through templates. It's a useful tool to  get you up and running quickly with a project structure and source files that can be modified afterward.

![](https://i.imgur.com/YE41SyD.png)

Windows Template Studio will generate UWP applications based upon the attribute sets you specify. These attribute sets determine the various characteristics of the application such as its UI navigation style, supporting frameworks, application pages, and Windows 10 features.

![](https://i.imgur.com/Ffoj4T9.png)

### Accessibility Tools

The [Windows Software Development Kit][2] (SDK) provides a number of excellent tools that can be used to test the accessibility of UWP applications. These tools can be used to track events, verify accessibility requirements, and probe accessbility-based data.

**Accessible Event Watcher (AccEvent)**: This tool can be used to track the events raised by UI elements within an application.

![](https://i.imgur.com/4hQ4k7U.png)

**UI Accessibility Checker (AccChecker)**: A tool that verifies that key UI accessibility requirements are met in the design and implementation of UI Automation (UIA) or Microsoft Active Accessibility (MSAA) regardless of the underlying UI framework.

![](https://i.imgur.com/8RXQYNx.png)

**Inspect Object (Inspect.exe)**: A tool that allows you to select any UI element and view its accessibility data.

**UI Automation Verify**: Testing framework for manual and automated testing the implementation of Microsoft UI Automation by a control or application.

![](https://i.imgur.com/5sgm71l.png)

[0]: https://microsoft.com/store/apps
[1]: https://en.wikipedia.org/wiki/Universal_Windows_Platform
[2]: https://en.wikipedia.org/wiki/Microsoft_Windows_SDK
[3]: https://www.telerik.com/universal-windows-platform-ui
[4]: https://developer.microsoft.com/en-us/windows/bridges/desktop
[5]: https://adobe.com/products/xd.html
