Write some code
Get started with Hello, World.

Open a command prompt and cd to your home directory.

On Linux or Mac:
cd

On Windows:
cd %HOMEPATH%

Create a hello directory for your first Go source code.

For example, use the following commands:

mkdir hello
cd hello

Enable dependency tracking for your code.
When your code imports packages contained in other modules, you manage those dependencies through your code's own module. That module is defined by a go.mod file that tracks the modules that provide those packages. That go.mod file stays with your code, including in your source code repository.

To enable dependency tracking for your code by creating a go.mod file, run the go mod init command, giving it the name of the module your code will be in. The name is the module's module path.

In actual development, the module path will typically be the repository location where your source code will be kept. For example, the module path might be github.com/mymodule. If you plan to publish your module for others to use, the module path must be a location from which Go tools can download your module. For more about naming a module with a module path, see Managing dependencies.

For the purposes of this tutorial, just use example/hello.

$ go mod init example/hello
go: creating new go.mod: module example/hello
In your text editor, create a file hello.go in which to write your code.
