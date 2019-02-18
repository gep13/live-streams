# Gary Ewan Park - Twitch

I have recently started streaming on [Twitch](https://www.twitch.tv/gep13), on topics such as Chocolatey, Cake, and general Windows Automation topics.  I intend this to be a weekly stream, on a Monday evening at 8pm (GMT), but this may be subject to change.  If you have any ideas for topics that you would like to see covered on one of these streams, then please feel to raise an issue in this repository, and I will do my best to cover them in a future streams.

## Upcoming streams

| Date                         | Topic                                                  |
|------------------------------|--------------------------------------------------------|
| 25th February 2019 - 8PM GMT | Creating a new Visual Studio Code Extension - Part 2   |
| 4th March 2019 - 8PM GMT     | Getting started with PoshBot - Create Plugin           |

## Past streams

### Monday 18th February 2019

[![Monday 18th February 2019 - Live Stream](http://img.youtube.com/vi/-RzIhqOloic/0.jpg)](http://www.youtube.com/watch?v=-RzIhqOloic "Monday 18th February 2019 - Live Stream")

In this stream, I started building a new VSCode Extension.  The function of this extension is to take the contents of the clipboard, and upload it to Azure Storage, and then output a markdown snippet to the current open markdown file.  This will dramatically improve the workflow that I use for writing blog posts, documentation, etc.

The stream started with using the yeoman generator to scaffold out a new VSCode extension, and then make use of the Cake.VsCode.Recipe package for Cake to run a build of the extension, and generate the vsix file.  This was then connected to AppVeyor, so that every commit to the GitHub repository results in a build being executed.

The commits that were completed in this stream can be found here:

- https://github.com/gep13/clipimg-vscode/commit/a8ce60f9c4b75d2505917460d911249f6e97a6f7
- https://github.com/gep13/clipimg-vscode/commit/7f1db4cd7188ab14a92f4f71cbdc9fd286eac518
- https://github.com/gep13/clipimg-vscode/commit/13e9ab0814d8116b9604425fa9a2d8c130907161
- https://github.com/gep13/clipimg-vscode/commit/4c80e8a06bab0e87983037f059ede232987d11cd

Setting up of the AppVeyor build results in some failures, which were as a result of a bug in the Cake.VsCode.Recipe package.  An issue was created here:

https://github.com/cake-contrib/Cake.VsCode.Recipe/issues/2

to cover this.

### Monday 11th February 2019

[![Monday 11th February 2019 - Live Stream](http://img.youtube.com/vi/rucgfNjxzog/0.jpg)](http://www.youtube.com/watch?v=rucgfNjxzog "Monday 11th February 2019 - Live Stream")

In this stream, I was joined by [Martin Björkström](https://twitter.com/mholo65), and we started looking at implementing a C# Language Server for validating a Chocolatey nuspec file which is opened within Visual Studio Code.  This used two nuget packages:

* https://www.nuget.org/packages/OmniSharp.Extensions.LanguageProtocol/
  * for creating/instantiating the Language Server
* https://www.nuget.org/packages/GuiLabs.Language.Xml/
  * for parsing the XML of the nuspec file

The code that was discussed in this stream can be found in this [repository](https://github.com/mholo65/nuspec-lsp), which Martin created.  This shows the complete prototype of the C# Language Server running within Visual Studio Code, and validating the nuspec using the Schema and also a custom rule for templated attributes.

More information about the official Language Server Protocol can be found [here](https://microsoft.github.io/language-server-protocol/).

And the blog post that Martin mentioned in the stream about creating a Language Server can be found [here](https://martinbjorkstrom.com/posts/2018-11-29-creating-a-language-server)

### Monday 4th February 2019

[![Monday 4th February 2019 - Live Stream](http://img.youtube.com/vi/6roxDdoRZ_I/0.jpg)](http://www.youtube.com/watch?v=6roxDdoRZ_I "Monday 4th February 2019 - Live Stream")

In this stream, we delved into the [Spectre.Cli](https://www.nuget.org/packages/Spectre.Cli/) library, and how it can be applied to an existing command line application, in the form of [GitReleaseManager](https://github.com/gittools/gitreleasemanager).

This was my first stream with a guest on the show.  This was [Patrik Svensson](https://twitter.com/firstdrafthell), the creator of the Spectre.Cli library.

This stream consisted of showing how to go about setting up Spectre.Cli, and showing how to begin creating the command structure that a CLI application will use.

The output from this live-stream can be seen in this commit here:

https://github.com/GitTools/GitReleaseManager/commit/4d1e3ae53bdcb2481fc588ae9348ab72a535757e

There is still some work that needs to be done here to finish off this work, including creation of additional commands as well as the settings for each command, however, the framework for all of this has been laid, so it should be reasonably simple to implement.  As mentioned on the stream, a good example of everything that can be done with Spectre.Cli can be seen in this PR:

https://github.com/cake-build/cake/pull/2334

Which is re-writing the Cake command line parsing to use Spectre.Cli.

### Monday 21st January 2019

[![Monday 21st January 2019 - Live Stream](http://img.youtube.com/vi/ppc3eZtILVM/0.jpg)](http://www.youtube.com/watch?v=ppc3eZtILVM "Monday 21st January 2019 - Live Stream")

In this stream, we continued talking about how to extend the Chocolatey CLI with a new command, `choco export`.

This included a brief discussion about how Unit Testing is done on the Chocolatey code base, and the need to install the NUnit 2 Test Adapter so that the Test Explorer reports success/failure correctly.

There was a little bit of a side line discussion about the correct encoding to apply to a file, which we eventually got figured out.

The output from this live-stream can be seen in this commit here:

https://github.com/gep13/choco/commit/b5fa2f079700dab1f6e347df57ba93b1b64cc44a

There is still some work that needs to be done here to finish off this work, but the additional arguments that have been added make it much more functional.

### Monday 14th January 2019

[![Monday 14th January 2019 - Live Stream](http://img.youtube.com/vi/jFozwL8qizU/0.jpg)](http://www.youtube.com/watch?v=jFozwL8qizU "Monday 14th January 2019 - Live Stream")

In this stream, we talked about how to get started with the Chocolatey Source Code, highlighting a couple of known stumbling blocks that people run into.

* Missing SolutionVersion.cs file
* Requirement to install dotnet 3.5
* Running with a second instance of Chocolatey

From there, we started implementing a new Export command, that can be used to export the current list of packages into a packages.config, which could then be passed into the `choco install` command on another machine, or when re-building current machine.

The output from this live-stream can be seen in this commit here:

https://github.com/gep13/choco/commit/9ca6f01b6f7619a438833e3c01107ad0e7bd6a3a

There is still some work that needs to be done here to finish off this work, but it is at least functional for this first pass.

### Monday 7th January 2019

[![Monday 7th January 2019 - Live Stream](http://img.youtube.com/vi/bwZBWzABynU/0.jpg)](http://www.youtube.com/watch?v=bwZBWzABynU "Monday 7th January 2019 - Live Stream")

In this live stream, we talked about the end to end process of setting up a complete CI/CD pipeline for a new Cake addin.  The included setting up of:

* Appveyor
* Cake.Recipe
* xUnit Tests
* Code Coverage with OpenCover
* Publishing Code Coverage metrics to coveralls.io
* Mergify
* Dependabot
* GitVersion
* GitReleaseManager

At the end of the video, the new Cake addin was successfully submitted to NuGet.org as part of the release, and a tweet and Gitter message were automatically sent out to the community to let them know that the addin is available.

### Monday 17th December 2018

[![Monday 17th December 2018 - Live Stream](http://img.youtube.com/vi/35JiK0AdGqM/0.jpg)](http://www.youtube.com/watch?v=35JiK0AdGqM "Monday 17th December 2018 - Live Stream")

In this stream, we talked about how the Moderation Process for the Chocolatey Community Repository works.  This included the automated services that occur, including package_verifier, package_validator, package_scanner and package_cacher.  Following that, we discussed the manual review process that happens by one of the moderators of the Community Repository.  Finally, we addressed the usage of the package_cleanup service for tidying up unmaintained packages, and finally, using the Chocolatey Test Environment when creating/maintaining packages.

### Monday 10th December 2018

[![Monday 10th December 2018 - Live Stream](http://img.youtube.com/vi/_AVfJsVmf9g/0.jpg)](http://www.youtube.com/watch?v=_AVfJsVmf9g "Monday 10th December 2018 - Live Stream")

In this stream, we talked about how to use Sonatypes Nexus Repository to cache packages from the Chocolatey Community Package Repository locally on your machine/environment, so that they don't need to be downloaded each time they are required.  This can help if you are running into the newly implemented [Rate Limiting](https://chocolatey.org/docs/community-packages-disclaimer#rate-limiting) feature on chocolatey.org.
