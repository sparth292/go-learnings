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

This is your Go code. In this code, you:

Declare a main package (a package is a way to group functions, and it's made up of all the files in the same directory).
Import the popular fmt package, which contains functions for formatting text, including printing to the console. This package is one of the standard library packages you got when you installed Go.
Implement a main function to print a message to the console. A main function executes by default when you run the main package.
Run your code to see the greeting.
$ go run .

Hello, World!

The go run command is one of many go commands you'll use to get things done with Go. Use the following command to get a list of the others:

$ go help

Call code in an external package
When you need your code to do something that might have been implemented by someone else, you can look for a package that has functions you can use in your code.

Make your printed message a little more interesting with a function from an external module.
Visit pkg.go.dev and search for a "quote" package.
In the search results, locate and click on the v1 of the rsc.io/quote package (it should be listed with the "Other major versions" of rsc.io/quote/v4).
In the Documentation section, under Index, note the list of functions you can call from your code. You'll use the Go function.
At the top of this page, note that package quote is included in the rsc.io/quote module.
You can use the pkg.go.dev site to find published modules whose packages have functions you can use in your own code. Packages are published in modules -- like rsc.io/quote -- where others can use them. Modules are improved with new versions over time, and you can upgrade your code to use the improved versions.

In your Go code, import the rsc.io/quote package and add a call to its Go function.
After adding the highlighted lines, your code should include the following:
