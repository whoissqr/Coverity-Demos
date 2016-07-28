# Coverity Build Integration Demos

This repository contains minimal projects that utilize various build systems (e.g. make, ant, maven, gradle). Each has a single "HelloWorld" source file and a build configuration that will compile and clean the project.

Each project also has a script that produces semi-automated demonstration of how Coverity integrates with each of these build systems. This allows you to demonstrate the build/analyze/commit cycle using the toolchain that your audience is most familiar with.

## Prerequisites

Although the commands used during the demonstration are recorded, the playback is live. Therefore, you must actually have the toolchain installed for each of the build systems. For example, you'll need to install gcc and make to run the make demonstration. Or you'll need to install a JDK and Maven to run the mvn demonstration. How you install the toolchain is up to you. However, the binaries must be located in your PATH so the demonstration tools can find them.

You'll also need to install [Cleo](https://metacpan.org/pod/App::Cleo), which is a simple utility for interactively playing out a series of pre-recorded commands. Cleo can be installed with either of these commands:

```
curl -sL cpanmin.us | sudo perl - App::Cleo
wget -qO - cpanmin.us | sudo perl - App::Cleo
```

Lastly, each demonstration concludes by committing the results to a Coverity stream named "demo" on the localhost. Therefore, you'll need to be running a Coverity server and have a "demo" stream set up. It will also need an `admin` account with `coverity` as the password.

## Usage

To start a demonstration, open a terminal and navigate to the directory that contains the appropriate project for your needs. Then give this command: `cleo demo`. Once the demonstration has started, press space to step through the commands. Some commands are broken into chunks and the demonstration pauses so you can explain that part of the command.  Whenever the demonstration pauses, press space to continue.

Each demo is roughly the same: show the source; show the builder; run the cov commands.  But you can add commands as appropriate for your situation. You can also customize the playback in several differnt ways. Say `man cleo` or refer to the [online documentation](https://metacpan.org/pod/distribution/App-Cleo/bin/cleo) for more information on that.

