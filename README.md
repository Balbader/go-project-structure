`cmd`: contains the main applications or binaries that are meant to be executed. In this case, there is only one application, app, and it is located in a subdirectory named cmd/app. The main.go file contains the entry point of the application.

`internal`: contains the internal packages that should not be imported by the applications outside of the project. It's organized into several subdirectories, each with a specific responsibility:

`api`: contains the HTTP API implementation. Notice that there is a possibility to add other API implementations, like gRPC.

`config`: contains the configuration package. Environment variables are loaded into config and are used from there. Parts of config are passed down to lower layers.

`util`: contains the utility package that consists of smaller helper functions.

`pkg`: contains the packages that can be imported and used by other Go projects. It's organized into several subdirectories, each with a specific responsibility:

`admin`: contains the package that implements the admin functionality. Packages categorized by business function can be added at this level in any quantity.

`admin/repository`: contains the package that implements the admin repository. The repository layer is that it should be accessed through an interface, so the implementation can be easily replaced when it’s needed.

`admin/service`: contains the package that implements the admin service.

`scripts`: contains scripts used for building, testing, and running the application.

`deployment`: contains the deployment files for the application, including a Dockerfile, a docker-compose file, and a Kubernetes file.

`.env`: contains the environment variables used by the application.

`Makefile`: contains the makefile used to build, test, and run the application. In addition to other functionalities, including mock and documentation generation in this file can be beneficial.

`README.md`: contains the documentation for the application.

`go.mod` and `go.sum`: contain the Go module definition and the checksums of the dependencies.
