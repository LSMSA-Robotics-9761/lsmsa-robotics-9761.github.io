---
title: Overview of software used
nav_order: 1
---

# Overview of software used
{: .no_toc }

{% include toc.md %}

## Core software components

This is a list of the most important software that should be installed on any computer that is to be used to control and/or program the robot. A list of some of the software components used can be read [here](https://docs.wpilib.org/en/stable/stubs/software-tools-stub.html).

### FRC Game Tools

A package of required components for use at FRC competitions. Full list of components available [here](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/frc-game-tools.html#installing-the-frc-game-tools).

[Installation](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/frc-game-tools.html){: .btn .btn-green-200}
[Download](https://www.ni.com/en/support/downloads/drivers/download.frc-game-tools.html){: .btn .text-green-200}

#### FRC Driver Station
{: .no_toc }

This app is used to communicate with and operate the robot. Drivers can enable/disable the robot, change its mode, diagnose connection and controller info, and view robot logs. It requires administrative permissions and gives the user a UAC prompt when opening. It is also required at competitions, as it is the only application allowed to communicate with the robot during FRC competitions.

[Documentation](https://docs.wpilib.org/en/stable/docs/software/driverstation/index.html){: .btn .btn-blue-200}

#### roboRIO Imaging Tool
{: .no_toc }

Used to image a roboRIO 1. However, we use a roboRIO 2 so this tool is not required (see [Imaging your roboRIO 2](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/roborio2-imaging.html)) It can, however, be used to set the team number of both a roboRIO 1 and roboRIO2

[Documentation](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/imaging-your-roborio.html){: .btn .btn-blue-200}

### WPILib

A package of required software for controlling a robot when using the Java or C++ programming language. Full list of components available [here](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/wpilib-setup.html#what-is-installed).

[Installation](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/wpilib-setup.html){: .btn .btn-green-200}
[Documentation](https://docs.wpilib.org/en/stable/index.html){: .btn .btn-blue-200}

{: .note-title}
> API Reference Documentation is available for:
> - [Java](https://github.wpilib.org/allwpilib/docs/release/java/index.html)
> - [C++](https://github.wpilib.org/allwpilib/docs/release/cpp/index.html)
> - [Python](https://robotpy.readthedocs.io/projects/robotpy/en/stable/)

#### Visual Studio Code
{: .no_toc }

The IDE used for programming the robot. Installs a separate copy of VS Code separate from the one that's already installed on your computer. The difference is that it has the necessary extensions for robot code development, these being WPILib and Java/C++/Python extensions.

[Documentation (from WPILib)](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/index.html){: .btn .btn-blue-200}
[Documentation (official)](https://code.visualstudio.com/docs){: .btn .btn-blue-100}

{: .tip-title}
> Question: Why does WPILib install a separate copy of VS Code?
>
> - Official answer: "The offline installer sets up a separate copy of VS Code for WPILib development, even if you already have VS Code on your machine. This is done because some of the settings that make the WPILib setup work may break existing workflows if you use VS Code for other projects."
> - Real answer: The people who make WPILib are too lazy to figure out how to use VS Code's [Profiles](https://code.visualstudio.com/docs/configure/profiles) feature. If you don't want to have multiple copies of VS Code on your computer, you can install the VS Code extensions into a separate profile on your main copy of VS Code by manually extracting and installing the extensions. See below for info on how to do that.
>
> {: .opaque }
> <div markdown="block">
> {: .note-title}
>> <details markdown="block">
>>   <summary>
>>     How to install WPILib extensions into main copy of VS Code
>>   </summary>
>>   {: .text-delta }
>>   1.  Download and mount the WPILib ISO file as normal
>>   2.  Extract the artifacts ZIP file named `WPILib_Windows-XXXX.X.X-artifacts.zip` (where the X's are replaced with the WPILib version number). You will need to extract it to a different directory on your computer, as you cannot extract it to the mounted disk.
>>   3.  In the extracted folder, navigate to the `vsCodeExtensions` folder. Note this location for later.
>>   4.  In VS Code, create a new profile by running the `Profiles: New Profile...` command. Name it WPILib, give it an icon, and optionally copy from another profile (like the Default profile) so that your settings, keyboard shortcuts, and themes are kept. Then, click the Create button.
>>   5.  Wait for VS Code to create the profile. Depending on whether or not you are copying from another profile, this may take a while.
>>   6.  Install the WPILib extensions by running the `Extensions: Install from VSIX...` command, navigating to the `vsCodeExtensions` folder you found earlier, selecting all of the files inside it, and clicking Install.
>>   7.  After the extensions are installed, you may need to restart VS Code by running the `Developer: Reload Window` command.
>> </details>

#### WPILib Tools
{: .no_toc }

These are separate apps that are installed to your computer. They can be launched by finding where the app is located on your computer, or using the `WPILib: Start Tool` command in VS Code. Below is a list of all the different tools and what they're used for.

##### Dashboards
{: .no_toc }

Apps that are used to read data from the robot. For more info, see [Choosing a Dashboard](https://docs.wpilib.org/en/stable/docs/software/dashboards/dashboard-intro.html)

- [SmartDashboard](https://docs.wpilib.org/en/stable/docs/software/dashboards/smartdashboard/index.html) - (Driver Dashboard) Simplest dashboard that allows you to quickly log data values without using something archaic like `System.out.println()`. If you've ever used variables in Scratch before, SmartDashboard looks and behaves somewhat similarly to its variable monitors. Most (if not all) of the other dashboards on this list are able to view data from SmartDashboard via the [NetworkTables](https://docs.wpilib.org/en/stable/docs/software/networktables/index.html) API. Therefore, it's arguably important to learn how to use SmartDashboard first.
- [Shuffleboard](https://docs.wpilib.org/en/stable/docs/software/dashboards/shuffleboard/index.html) - (Driver/Programming Dashboard) A more modern and advanced dashboard. This app is best used to display important information about the robot to the driver; for example, whether the robot's Swerve Drive is driving robot-orientated or field-orientated. It does this by viewing data from SmartDashboard (via NetworkTables).
- [Elastic](https://docs.wpilib.org/en/stable/docs/software/dashboards/elastic.html) - (Driver Dashboard) An alternative dashboard that serves the same purpose as Shuffleboard. It views data from SmartDashboard (via NetworkTables).
- [Glass](https://docs.wpilib.org/en/stable/docs/software/dashboards/glass/index.html) - (Programming Dashboard) A dashboard built using the ImGui GUI library. It looks and works similarly to the Sim GUI when running robot simulations. It can be used to view data from SmartDashboard (via NetworkTables) in a more modern and advanced interface.
- [AdvantageScope](https://docs.wpilib.org/en/stable/docs/software/dashboards/advantagescope.html) - (Programming Dashboard) An advanced yet intuitive dashboard that has different specialized tabs that allow programmers to analyze data points about a robot during operation or afterwards. It can connect to several data sources, including:
  - [NetworkTables](https://docs.wpilib.org/en/stable/docs/software/networktables/index.html) - The API used by SmartDashboard
  - [AdvantageKit](https://docs.advantagekit.org/) - A bit more involved to set up, but it does have many benefits if your programmers need an in-depth way to analyze everything about the robot.
  - And a few more, which you can see in list located [here](https://docs.advantagekit.org/).

##### Other Utilities
{: .no_toc }

Various apps used for miscellaneous tasks. Some of their functionality may be available in the aforementioned dashboards.

- [RobotBuilder](https://docs.wpilib.org/en/stable/docs/software/wpilib-tools/robotbuilder/index.html) - A utility that can be used to make planning the robot easier. It can generate robot code, wiring diagrams, and more. It is used to plan the robot and its subsystems.
- [OutlineViewer](https://docs.wpilib.org/en/stable/docs/software/wpilib-tools/outlineviewer/index.html) - A utility used to view and modify the contents of the [NetworkTables](https://docs.wpilib.org/en/stable/docs/software/networktables/index.html) API. It is used for debugging purposes.
- [PathWeaver](https://docs.wpilib.org/en/stable/docs/software/pathplanning/pathweaver/index.html) - A utility used to generate trajectories that control how the robot moves in Autonomous mode.
  - Deprecated and will be removed for 2027
  - Alternatives: [Choreo](https://docs.wpilib.org/en/stable/docs/software/pathplanning/choreo/index.html), [PathPlanner](https://github.com/mjansen4857/pathplanner)
- [SysId](https://docs.wpilib.org/en/stable/docs/software/advanced-controls/system-identification/index.html) - A utility that is used for [System Identification](https://docs.wpilib.org/en/stable/docs/software/advanced-controls/controls-glossary.html#term-system-identification). Basically, this tool accurately calculate exactly how much voltage is required to power a motor for simple motor setups, elevators, and arms. If this is too complicated, tried and true trial-and-error can get the trick done.
- [Data Log Tool](https://docs.wpilib.org/en/stable/docs/software/telemetry/datalog-download.html#managing-data-logs-with-the-datalogtool) - A utility used to download log files off of the roboRIO via SSH. It is a SFTP client.
  - Alternatives: You can download logs using AdvantageScope (read [here](https://docs.advantagescope.org/getting-started/manage-files/#downloading-from-a-roborio)).
- [roboRIO Team Number Setter](https://docs.wpilib.org/en/stable/docs/software/wpilib-tools/roborio-team-number-setter/index.html) - A simple utility that can be used to set the team number on a roboRIO, reboot a roboRIO, and enable/disable a roboRIO's configuration webpage. That's it.
  - Alternatives: You can set a roboRIO's team number using the roboRIO Imaging Tool (read [here](https://docs.wpilib.org/en/stable/docs/software/advanced-controls/controls-glossary.html#term-system-identification))
- [WPIcal](https://docs.wpilib.org/en/stable/docs/software/wpilib-tools/wpical/index.html) - A utility used to calibrate AprilTags on the field.

## 3rd party libraries

Although the breadth of WPILib is huge, it (obviously) can't support managing 3rd party devices. Therefore, these 3rd party companies create software libraries that can be installed and supplement WPILib when programming.

Libraries can be installed by finding them in the "Available Dependencies" list under the "WPILib Vendor Dependencies" tab on VS Code. For more information, read [3rd Party Libraries](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/3rd-party-libraries.html).

Below is a list of libraries that we commonly use:

- REVLib
- CTRE-Phoenix (v6)
- Studica

#### REVLib
{: .no_toc }

Used to read data from and control certain REV Robotics devices.

[Documentation](https://docs.revrobotics.com/revlib){: .btn .btn-blue-200}

{: .note-title}
> API Reference Documentation is available for:
> - [Java](https://codedocs.revrobotics.com/java/com/revrobotics/package-summary.html)
> - [C++](https://codedocs.revrobotics.com/cpp/namespacerev.html)

Notably, we use REVLib for the following devices:

- [SPARK MAX](https://docs.revrobotics.com/rev-hardware-client/ion/spark-max)

#### CTRE-Phoenix (v6)
{: .no_toc }

Used to read data from and control certain CTRE Phoenix devices

[Documentation](https://v6.docs.ctr-electronics.com/en/stable/){: .btn .btn-blue-200}
[API Documentation](https://v6.docs.ctr-electronics.com/en/stable/docs/api-reference/index.html){: .btn .btn-blue-100}

{: .note-title}
> API Reference Documentation is available for:
> - [Java](https://api.ctr-electronics.com/phoenix6/release/java/)
> - [C++](https://api.ctr-electronics.com/phoenix6/release/cpp/)
> - [Python](https://api.ctr-electronics.com/phoenix6/release/python/)

Notably, we use CTRE-Phoenix (v6) for the following devices:

- [CANcoder](https://v6.docs.ctr-electronics.com/en/stable/docs/hardware-reference/cancoder/index.html)

#### Studica
{: .no_toc }

Used to read data from and control certain Studica devices

[Offline Installation for Java](https://www.studica.com/java){: .btn .btn-green-200}

{: .note-title}
> API Reference Documentation is available for:
> - [Java](https://dev.studica.com/releases/JavaAPIDocs/annotated.html)
> - [C++](https://dev.studica.com/releases/JavaAPIDocs/annotated.html)
> 
> There is no comprehensive documentation, so you'll just have to use these API reference docs.

Notably, we use Studica for the following devices:

- [navX2-MXP](https://pdocs.kauailabs.com/navx-mxp/)

## Hardware utility software

This is a list of helpful software that are used to manage physical hardware from different companies. Listed here are the hardware utility software for REV Robotics, CTR Electronics (Phoenix Tuner X), and Studica/Kauai Labs.

#### REV Hardware Client
{: .no_toc }

A utility app used to manage REV devices. It can update firmware for REV devices, manage configuration stored on those devices, and test a device while providing feedback via data and graphs (available via the [Telemetry Tab](https://docs.revrobotics.com/rev-hardware-client/ion/telemetry))

[Installation](https://docs.revrobotics.com/rev-hardware-client/gs/install){: .btn .btn-green-200}
[Documentation](https://docs.revrobotics.com/rev-hardware-client){: .btn .btn-blue-200}

Notably, we use REV Hardware Client for the following devices:

- [SPARK MAX](https://docs.revrobotics.com/rev-hardware-client/ion/spark-max)
- [Power Distribution Hub](https://docs.revrobotics.com/rev-hardware-client/ion/power-distribution-hub)
- [Pneumatic Hub](https://docs.revrobotics.com/rev-hardware-client/ion/pneumatic-hub)

#### Phoenix Tuner X
{: .no_toc }

A utility app for managing CTR Electronics devices. It can update firmware, manage configuration stored on those devices, test a device, and view data and graphs about a device.

{: .tip-title}
> Installation is available on:
> 
> [Microsoft Store](https://apps.microsoft.com/detail/9nvv4pwdw27z){: .btn .btn-green-200}
> [Google Play Store](https://play.google.com/store/apps/details?id=com.ctre.phoenix_tuner){: .btn .btn-green-200}
> [Apple App Store ($3.99)](https://apps.apple.com/us/app/phoenix-tuner-x/id6502530040){: .btn .btn-green-200} 
> 
> I imagine the version on the Apple App Store is paid is because of Apple's Developer Program that costs $99 annually. Just use the free versions for Windows and Android devices.

[Documentation](https://v6.docs.ctr-electronics.com/en/stable/docs/tuner/index.html){: .btn .btn-blue-200}

Notably, we use Phoenix Tuner X for the following devices:

- [CANcoder](https://v6.docs.ctr-electronics.com/en/stable/docs/hardware-reference/cancoder/index.html)

#### Studica Hardware Manager
{: .no_toc }

A utility app that can be used to configure and update Studica devices.

{: .warning}
> For some reason, there is... LITERALLY no info about this software on the Internet. I'm not even sure how I found it (that's a lie, I found it in the repository below). I'm not sure if this is unreleased beta software or something... but it's VERY strange.
>
> What's also strange is that it appears to be an Electron app that—for some really strange reason—displays a website that is viewable at `localhost:3000`! Now I've never created an Electron app, but I know that there's something really wrong here.

[Direct download](https://dev.studica.com/maven/release/firmware/app/win32/Studica_Hardware_Manager-Setup_1.0.0.exe){: .btn .btn-green-200}
[Repository](https://github.com/Studica-Robotics/NavX){: .btn}

Documentation is located in-app under the "Help and Support" tab.

Alternatives:
- [navXUI](https://pdocs.kauailabs.com/navx-mxp/software/navx-mxp-ui/)

Notably, we use Studica Hardware Manager for the following devices:

- [navX2-MXP](https://pdocs.kauailabs.com/navx-mxp/)

## Supplemental software components

There are some software components that may not necessarily fit in any of the aforementioned categories or you may not end up using at all. They are listed here for breadth.

#### Microsoft Visual C++
{: .no_toc }

Microsoft Visual C++ (MSVC) is used when building projects with WPILib. Yes, it is also used for Java projects. You can read more info about this topic [here](https://docs.wpilib.org/en/stable/docs/software/advanced-gradlerio/jvm-runtime.html).

If you get an error complaining about an invalid MSVC runtime version and you've exhausted your options in the aforementioned documentation page, try installing the MSVC Redistributable and see if that fixes your problems.

[Installation](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version){: .btn .btn-green-200}

You will probably install the version for x64 architecture. If you're running 32-bit Windows, you'll want the version for x86 architecture.

#### balenaEtcher
{: .no_toc }

This is an app used to flash image files onto hardware devices like flash drives and SD cards. In the context of FRC, it is used to flash the firmware for the roboRIO onto a microSD card. The guide for doing this is available [here](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/roborio2-imaging.html).

[Installation](https://etcher.balena.io/#download-etcher){: .btn .btn-green-200}
