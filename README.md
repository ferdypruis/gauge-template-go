# gauge-template-go

Sample template for getting started with [Gauge](https://github.com/getgauge/gauge) and the [Go language runner](https://github.com/getgauge-contrib/gauge-go).

## Usage
Install the template
```
gauge template go https://github.com/ferdypruis/gauge-template-go/archive/refs/tags/v1.0.0.zip
```

Then init a new project as normal
```
gauge init go
```

The _stepimpl.go_ was copied from https://github.com/getgauge-contrib/gauge-go/blob/master/stepImpl/stepImplementation.go.


# Installing Go language runner plugin
If you try to install the Go language runner plugin on a recent version of Go, Gauge exits with the following error;

    root@356636ffd58b:/go# gauge install go
    .......................
    go: go.mod file not found in current directory or any parent directory.
            'go get' is no longer supported outside a module.
            To build and install a command, use 'go install' with a version,
            like 'go install example.com/cmd@latest'
            For more information, see https://golang.org/doc/go-get-install-deprecation
            or run 'go help get' or 'go help install'.
    Failed to install plugin 'go' version 0.3.1.
    Reason: exit status 1

To circumvent this until this gets fixed, temporarily disable Go modules while installing the plugin by setting the environment variable `GO111MODULE` to "off";

    root@356636ffd58b:/go# GO111MODULE="off" gauge install go
    .......................
    
    Successfully installed plugin 'go' version 0.3.1
    
[Here is a Dockerfile](https://gist.github.com/ferdypruis/ef55ec2fb9cf3d161a8b5af770a4a714) with Gauge and Go which I use in my CI/CD pipeline.
