# Welcome to OpenSim!

## Overview

OpenSim is a BSD Licensed Open Source project to develop a functioning virtual worlds server platform capable of supporting multiple clients and servers in a heterogeneous grid structure. OpenSim is written in C#, and can run under Mono or the Microsoft .NET runtimes.

See the [Opensim wiki](http://opensimulator.org/wiki/Main_Page) for more details.

## Compiling OpenSim

See [BUILDING.txt](http://opensimulator.org/wiki/BUILDING) if you downloaded a source distribution and need to build OpenSim before running it.

## Running OpenSim on Windows

We recommend that you run OpenSim from a command prompt on Windows in order to capture any errors.

### To run OpenSim from a command prompt:

1. cd to the `bin/` directory where you unpacked OpenSim.
2. Run `OpenSim.exe`.

Now see the "Configuring OpenSim" section.

## Running OpenSim on Linux

You will need Mono >= 2.4.2 to run OpenSim. On some Linux distributions, you may need to install additional packages. See [Dependencies](http://opensimulator.org/wiki/Dependencies) for more information.

### To run OpenSim:

1. cd bin
2. `mono OpenSim.exe`

Now see the "Configuring OpenSim" section.

## Configuring OpenSim

When OpenSim starts for the first time, you will be prompted with a series of questions that look something like:

[09-17 03:54:40] DEFAULT REGION CONFIG: Simulator Name [OpenSim Test]:

For all the options except simulator name, you can safely hit enter to accept the default if you want to connect using a client on the same machine or over your local network.

You will then be asked "Do you wish to join an existing estate?" If you're starting OpenSim for the first time, answer no (which is the default) and provide an estate name.

Shortly afterwards, you will be asked to enter an estate owner's first name, last name, password, and e-mail (which can be left blank). Do not forget these details; since initially only this account will be able to manage your region in-world. You can also use these details to perform your first login.

Once you are presented with a prompt that looks like:

  Region (My region name) #

You have successfully started OpenSim.

If you want to create another user account to log in rather than the estate account, then type "create user" on the OpenSim console and follow the prompts.

**Helpful resources:**

* [Configuration](http://opensimulator.org/wiki/Configuration)
* [Configuring Regions](http://opensimulator.org/wiki/Configuring_Regions)

## Connecting to your OpenSim

By default, your sim will be available for login on port 9000. You can log in by adding `-loginuri http://127.0.0.1:9000` to the command that starts Second Life (e.g., in the Target box of the client icon properties on Windows). You can also log in using the network IP address of the machine running OpenSim (e.g., `http://192.168.1.2:9000`).

To log in, use the avatar details that you gave for your estate ownership or the one you set up using the "create user" command.

## Bug reports

If running under Mono: run `OpenSim.exe` with the `--debug` flag:

        mono --debug OpenSim.exe

## More Information on OpenSim

More extensive information on building, running, and configuring OpenSim, as well as how to report bugs and participate in the OpenSim project can always be found at [http://opensimulator.org](http://opensimulator.org).

Thanks for trying OpenSim; we hope it is a pleasant experience.
