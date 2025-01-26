# Setting up a dev container for Go

* Primary author: [Mani Pourfazli](https://github.com/manip1384)
* Reviewer: [Daniel Ramsgard](https://github.com/DanielRamsgard)

#### Before doing anything, make sure you have these installed:

1. `Docker Desktop` for mac, windows, or linux
2. `VS Code` for mac, windows, or linux
3. `Git` for mac, windows, or linux
4. A `Github` Account

#### Also make sure you have an understanding of these topics:

4. Some basic knowledge of [**Go Syntax**](https://www.w3schools.com/go/index.php).
5. Basic knowledge of the main [**Git Commands**](https://www.w3schools.com/git/) and syntax

#### Once you have those done it's time to make a directory to put your files into:

1. In the terminal run this command `mkdir <name>` (the name can be whatever you want it to be) to create a new directory. 
2. Now, to go into the directory you just made run this command `cd <name>`. (same name you made in the step above)
3. Once you have done that you need to create a git directory which can be done so by running `git init`.

#### Now make a github repo
1. Make a new public Github repo and copy the URL.
2. Run the following to initialize an empty Git repo:
```bash
git init
git remote add origin <GitHub Repo URL>
git fetch origin
git switch -c main
```

#### Now you need to set up your dev container. Follow these steps:

1. In VS Code, open your directory. You can do this by clicking on `File` then `Open Folder`
2. Now make sure you have the Dev Containers extension for VS Code. If you don't go ahead and install it
3. Create a `.devcontainer directory` in the root of your project with the following file inside: .devcontainer/devcontainer.json
4. Now put this inside the devcontainer.json file:
```
{
    "name": "Go Dev Container",
    "image": "mcr.microsoft.com/devcontainers/go:latest",
    "customizations": {
        "vscode": {
            "settings": {},
            "extensions": ["golang.go"]
        }
    }
}
```

#### Now you need to make a go file to put your code in:
1. Check the version of your Go by using `go --version`
2. Initialize a go module using `go mod init <your-project-name>`
2. Make a file in vscode called `main.go`
3. Open the file you just made and paste this inside:
```Go
package main
import "fmt"
func main() {
    fmt.Println("Hello COMP423")
}
```

#### Now run your program!!
1. You can press the `green play looking button` on VS Code to run your code or you can use this command: `go run main.go`
2. `go run` compiles and immediately runs the program and `go build` creates an executable binary that you can run separately, similar to compiling with gcc
3. Once you have done that, you should see the output: "Hello COMP423"


#### Now push your work to github
Do the following:
```bash
cd ..
echo "Go (Hello COMP423) program tutorial." > README.md
git add .
git commit -m "meaningful commit message"
git push origin main
```