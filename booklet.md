# lakeFS developer booklet

## Chapter 1: Following the quickstart section

### Goal: Follow the quickstart section on the documentation

Our documentation features a [Quickstart](https://docs.lakefs.io/quickstart/) section, allowing the user to experiment and learn about lakeFS.
Follow this section to get lakeFS up and running for the first time, add some data to it, and commit your changes.

### Goal: Improve the quickstart section

If something in the quickstart section is not clear, it needs to be improved! First, ask your buddy or another developer for clarifcation - and take note of what needs to change in the docs. Later, after you have cloned lakeFS - you can edit the documentation to include your improvements.

## Chapter 2: Your development environment

### Goal: Build and run lakeFS locally

Steps:
1. Install Go (see which version at the top of the go.mod file in the project root).
1. Clone lakeFS from GitHub.
1. From the project root, build the project using Make:
   ```
   make all
   ```
1. Install postgres
1. Create a config file similar to [this](https://docs.lakefs.io/reference/configuration.html#example-local-development) example, under the path ~/.lakefs.yaml.
1. From the project root, run lakeFS:
   ```
   ./lakefs run
   ```
 1. You should be able to browse to the UI from [http://localhost:8000](http://localhost:8000).


 ### Goal: Run lakeFS from your IDE

Open the project in your IDE (ask your buddy for an IntelliJ license), and run `cmd/lakefs/main.go`.
This file compiles to the binary we ran in the previous step. Don't forget to add the `run` argument.
Make sure you can access the UI.

### Goal: Create your first repository

### Goal: Create your first commit

### Goal: Upload and commit using the CLI

### Goal: Upload a file using the AWS client
