# lakeFS developer booklet

## Chapter 0: Become a fan

Give a GitHub star to the [lakeFS](https://github.com/treeverse/lakefs) repository, and to our other public repositories:
[boto-s3-router](https://github.com/treeverse/boto-s3-router), [terminus](https://github.com/treeverse/terminus), [charts](https://github.com/treeverse/charts), [blogs](https://github.com/treeverse/blogs) and [lakeview](https://github.com/treeverse/lakeview).

## Chapter 1: Following the quickstart section

### Goal: Follow the quickstart section on the documentation

Our documentation features a [Quickstart](https://docs.lakefs.io/quickstart/) section, allowing the user to experiment and learn about lakeFS.
Follow this section to get lakeFS up and running for the first time, add some data to it, and commit your changes.

### Goal: Improve the quickstart section

If something in the quickstart section is not clear, it needs to be improved! First, ask your buddy or another developer for clarification - and take note of what needs to change in the docs. Later, after you have cloned lakeFS - you can edit the documentation to include your improvements.

## Chapter 2: Your development environment

### Goal: Build and run lakeFS locally

Steps:
1. Install Go (see which version at the top of the go.mod file in the project root).
1. Install NodeJS.
1. Clone lakeFS from GitHub.
1. From the project root, build the project using Make:
   ```sh
   make all
   ```
1. Install postgres (or run using docker)
1. Create a config file similar to [this](https://docs.lakefs.io/reference/configuration.html#example-local-development) example, under the path ~/.lakefs.yaml. Note that the `blockstore.type` is now set to `local`. This means that lakeFS will save data on your local file system. That's good for development purposes.
   <br />[You might need to add a username and a password to the connection string if you initialized the DB with credentials: `connection_string: "postgres://<USER>:<PASSWORD>@localhost:5432..."`]
1. From the project root, run lakeFS:
   ```sh
   ./lakefs run
   ```
1. You should be able to browse to the UI from [http://localhost:8000](http://localhost:8000).


### Goal: Run lakeFS from your IDE

Open the project in your IDE (ask your buddy for an IntelliJ license), and run configuration for the file `cmd/lakefs/main.go`.
This file compiles to the binary we ran in the previous step. Don't forget to add the `run` argument.
Make sure you can access the UI.

### Goal: Use your local installation

#### Exploring the UI

From the web interface, create a repository in your local installation.

Use the UI to Upload a file to the repository, and explore the _Uncommitted Changes_ tab in the UI.
You can then commit the changes or revert them.

#### Using lakectl

### Goal: Upload a file using the AWS client

lakeFS exposes an S3-compatible API to operate on objects. That means we can use the AWS CLI to interact with lakeFS.
Follow the documentation in order to copy an object into your local installation.

Again, if something is not clear about the documentation, please take note of it.

## Chapter 3: lakeFS in the cloud

### Goal: Spin-up lakeFS using our Terraform configuration

Use our [Terraform configuration](https://github.com/treeverse/terraform/lakefs-on-ecs) to deploy lakeFS on AWS.
Make sure you can use the enviornment. Destroy it when done.

## Chapter 4: Under the Hood

### Goal: Use lakectl cat-sst to view the internals a commit

Prerequisite: complete the Graveler technical session.

### Goal: Use the stage/link API to add objects

### Goal: Use refs-dump and refs-restore to export and import data

### Goal: Use the [lakeFS Spark metadata client](https://github.com/treeverse/lakeFS/tree/master/clients/spark) to list objects

## Chapter 5: Advanced Feature

### Goal: use `lakefs import` and `lakectl ingest` to import data into lakeFS.

### Goal: export data from lakeFS to S3
