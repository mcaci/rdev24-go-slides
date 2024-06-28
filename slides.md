---
theme: seriph
background: /images/Gophers6.jpeg
title: Want to learn a new language? Let's Go!
info: |
  ## Want to learn a new language? Let's Go!
  Slides for Riviera DEV 2024
class: text-center
layout: cover
highlighter: shiki
drawings:
  persist: false
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
---

# Want to learn a new language? Let's Go!

<div class="absolute bottom-10 text-left">
    <div>Michele Caci</div>
    <div>Senior Software Engineer at Amadeus</div>
    <div class="flex m-0 gap-1">
      <a href="https://github.com/mcaci" target="_blank" alt="Michele's GitHub" title="Michele's GitHub"
        class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
        <carbon-logo-github />
      </a>
      <a href="https://x.com/goMicheleCaci" target="_blank" alt="Michele's X" title="Michele's X"
        class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
        <carbon-logo-x />
      </a>
      <a href="https://www.linkedin.com/in/michele-caci-47770132/" target="_blank" alt="Michele's Linkedin" title="Michele's Linkedin"
        class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
        <carbon-logo-linkedin />
      </a>
    </div>
</div>

<img src="/images/go-logo-blue.svg" class="absolute bottom-10 right-10 text-right"/>

---
transition: fade-out
layout: image-right
image: /images/michele.jpeg
backgroundSize: 80%
---

# Whoami

About myself

<v-clicks>

I’m a Gopher since 2018
- Practised via the [Tour of Go](https://go.dev/tour/) and [exercism](https://exercism.org/)

I work in Amadeus in a team that creates tooling in Go to assist applications deploying in the cloud

I speak at conferences, about Go and cloud topics

I previously worked in Java, Scala and C++

Besides programming I enjoy swimming, cooking and learning languages
- GOのワークショップへようこそ！

</v-clicks>

<!-- 
Bio: I'm Michele, Italian from Sicily, I am a passionate Gopher since 2018 and before then I used to work in Java, Scala and C++. I always like make side projects and develop new things when time let's me :D. Besides programming, I enjoy swimming, cooking and learning languages; currently, I'm learning Japanese: GOのワークショップへようこそ！ 

You can find me in:
- github: [mcaci](https://github.com/mcaci)
- linkedin: [Michele Caci](https://www.linkedin.com/in/michele-caci-47770132/)
- X/Twitter: [@goMicheleCaci](https://x.com/goMicheleCaci)
-->

---
transition: fade-out
layout: image-right
image: /images/hi.png
backgroundSize: 80%
---

# Let's get to know you

About you

Why do you want to learn Go?

What’s your background?

What do you expect from the workshop?

<v-click>

## Today’s plan

Learning Go basics theory and exercises

- Introduction
- The tools needed for today
- Make some gifs!

We will do pauses along the way

<img src="/images/RivieraDev.gif" class="absolute bottom-10 right-10 text-right" style="width: 50%; height: auto;"/>
</v-click>

---
transition: fade-out
layout: image-right
image: /images/Gophers10.jpeg
background-size: 80%
---

# The tools for today

- [Go](https://go.dev)
- The IDE of your choice
  - [Visual Studio Code](https://code.visualstudio.com/) with the [Go extension](https://code.visualstudio.com/docs/languages/go)
  - [Goland](https://www.jetbrains.com/go/)
  - Vim [plugin](https://github.com/fatih/vim-go)
- [pkg.go.dev](https://pkg.go.dev)
  - link to the documentation of Go packages
- [Git](https://git-scm.com/)
  - Optional: if you want to commit your changes

---
transition: fade-out
layout: image-right
image: /images/goAndMascotte.webp
background-size: 150%
---

# Go

A full ecosystem of language, toolchain and resources

<v-clicks depth="2">

- Developed at Google since 2009
  - Open source
- Similar to C/C++ but
  - Is garbage collected
  - Strives to provide a simpler syntax
  - Compiled executables almost as fast
- Builtin features
  - Concurrency
  - Unit tests, benchmark, fuzz tests, profiling
  - Package listing and documentation
  - Security checks and vulnerabilty database
  - Code formatter and linter, and so on

</v-clicks>

---
transition: fade-out
layout: lblue-fact
---

Let's Go: Hello World!

---
transition: fade-out
---

# Environment setup

Let's setup our first Go project

```bash
$ GIT_PLATFORM_URL=github.com; USER=mcaci; PROJECT_NAME=letsgo
$ mkdir -p ~/go/src/$GIT_PLATFORM_URL/$USER/$PROJECT_NAME && cd ~/go/src/$GIT_PLATFORM_URL/$USER/$PROJECT_NAME
$ go mod init
go: creating new go.mod: module github.com/mcaci/letsgo
$ git init # optional if you want to commit your code
```

We'll focus on two things here:

1. `go mod init`

Initializes a Go project as a [module](https://go.dev/ref/mod), a set of Go packages that can be imported by other Go modules

Creates a file `go.mod` that contains information about the go version used to compile our code and the dependencies that our module uses

2. __module github.com/mcaci/letsgo__

Go projects can be put anywhere but to make module creation and management easier we use the path `~/go/src/$GIT_PLATFORM_URL/$USER/$PROJECT_NAME` 

---
transition: fade-out
---

# Hello world!

Open your editor on the created folder and create a `main.go` file

Inside `main.go` write the following code

```go
package main

import “fmt”

func main() {
  fmt.Println(“Hello, world!”)
}
```

Then run 

```bash
$ go run main.go
Hello, world!
```

or

```bash
$ go build -o mymain main.go; ./mymain
Hello, world!
```

---
transition: fade-out
layout: two-cols-header
---

# Hello world!

Let's analyze the code

::left::

`package main` is a package declaration

A __package__ is a __set of symbols__ (functions, types, variables) that can be distributed to other packages to be used

It is mandatory as first instruction in every file

`import "fmt"` is an import declaration that states that we are using the __fmt__ package

`func main()` is the entrypoint of every Go application

`fmt.Println` is a function call that accepts a string and prints it to the screen

Syntax: _package_name.function_name_

::right::

```go{all|1|3|5-7|6|all}
package main

import “fmt”

func main() {
  fmt.Println(“Hello, world!”)
}
```

<v-click>
Notice that the `;` is not mandatory at the end of the line
</v-click>

<arrow v-click="[1, 2]" x1="350" y1="110" x2="195" y2="140" color="#953" width="2" arrowSize="1" />
<arrow v-click="[2, 3]" x1="350" y1="280" x2="195" y2="310" color="#953" width="2" arrowSize="1" />
<arrow v-click="[3, 4]" x1="330" y1="345" x2="175" y2="375" color="#953" width="2" arrowSize="1" />
<arrow v-click="[4, 5]" x1="330" y1="410" x2="175" y2="440" color="#953" width="2" arrowSize="1" />

<!-- 
Every go file starts with a package declaration
- Every folder is a package
- Tells in which package the code is located
func main(): the entrypoint
- Always located in package main
- Present only once
import statement
- Tells which packages are used in the file
fmt.Println is a function
- It prints a message (a string) to the screen
Function invocation
- package_name.function_name
“;” is not mandatory at the end of a statement

-->

---
transition: fade-out
layout: lblue-fact
---

Let's Go: Let's make our GIF application!

---
layout: fact
transition: fade-out
class: "font-size-7.8"
---

And making our code simpler is how we step up our Go game!

---
layout: lblue-end
transition: fade-out
---

<div class="text-white font-size-10">
Thank you very much!
</div>

<div class="absolute bottom-10">
  <div  class="text-white">Michele Caci</div>
  <div class="flex m-0 gap-1">
    <a href="https://github.com/mcaci" target="_blank" alt="Michele's GitHub" title="Michele's GitHub"
      class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
      <carbon-logo-github />
    </a>
    <a href="https://x.com/goMicheleCaci" target="_blank" alt="Michele's X" title="Michele's X"
      class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
      <carbon-logo-x />
    </a>
    <a href="https://www.linkedin.com/in/michele-caci-47770132/" target="_blank" alt="Michele's Linkedin" title="Michele's Linkedin"
      class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
      <carbon-logo-linkedin />
    </a>
  </div>
</div>