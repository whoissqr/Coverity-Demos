# Coverity Build Integration Demos

This repository contains minimal projects that utilize various build systems (e.g. make, ant, maven, gradle). Each has a single "HelloWorld" source file and a build configuration that will compile and clean the project.

Each project also has a script that produces semi-automated demonstration of how Coverity integrates with each of these build systems. This allows you to demonstrate the build/analyze/commit cycle using the toolchain that your audience is most familiar with.

## Prerequisites

Although the commands used during the demonstration are recorded, the playback is live. Therefore, you must actually have the toolchain installed for each of the build systems. For example, you'll need to install a JDK and Maven to run the mvn demonstration. How you install the toolchain is up to you. **NOTE:** the main executable binaries for the toolchain must be located in your PATH. 

You'll also need to install [Cleo](https://metacpan.org/pod/App::Cleo), which is a simple utility for interactively executing a sequence of pre-recorded commands. Cleo can be installed with either of these commands:

```
curl -sL cpanmin.us | sudo perl - App::Cleo
wget -qO - cpanmin.us | sudo perl - App::Cleo
```

Lastly, each demonstration concludes by committing the analysis results to a Coverity stream on the localhost. Therefore, you'll need to be running a Coverity server and have a stream named `demo` set up. It will also need an account named `demo` with `coverity` as the password.

## Usage

To use these demonstrations, you must clone this repository into your demo environment and install the prerequistes as described above. The demos work well on Linux but may also work on Windows via Cygwin.

To start a demonstration, open a terminal and navigate to the directory that contains the appropriate project for your needs. Then give the command: `cleo demo`. Once the demonstration has started, press space to step through the commands. Some commands are broken into chunks and the demonstration pauses so you can explain that part of the command.  Once again, press space to continue.

Each demo is roughly the same: show the source; show the builder; run the cov commands.  But you can add commands as appropriate for your situation. You can also customize the playback in several differnt ways. Say `man cleo` or refer to the [online documentation](https://metacpan.org/pod/distribution/App-Cleo/bin/cleo) for more information on that.

