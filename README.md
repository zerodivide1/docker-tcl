# docker-tcl
Ubuntu-based batteries-included Tcl for Docker

This contains most packages necessary for running Tcl 8.4
applications. It is based on an installation of the packages available
in Ubuntu. tclreadline is enabled by default for the root user in the
container so you will have a decent prompt at the command line.

This is a fork of the original [Tcl 8.6 docker-tcl project by efrecon](https://github.com/efrecon/docker-tcl).

# Building and Running

To build, simply write:

```
    docker build -t zerodivide1/tcl:8.4 .
```

To run and get an interactive Tcl prompt:

```
    docker run -it --rm zerodivide1/tcl:8.4
```

# Running your own scripts

This image exports `/opt/tcl` as a volume and arranges to give that
directory and its sub-directory `lib` as additional locations when
looking for packages.  This means that you should be able to mount
local directories onto `/opt/tcl` to run your own code within the
container.

Additionally, the image exports `/opt/data` to place random data that
you might wish to access from within the container.