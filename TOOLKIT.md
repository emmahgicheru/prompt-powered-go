# Prompt-Powered Kickstart: Getting Started with Go (Golang)

## Overview
This toolkit documents my experience learning **Go (Golang)** as a new programming language using **AI-assisted learning**. The goal of this project was to explore Go fundamentals, set up a working environment, and build a minimal runnable project while documenting how AI prompts supported my learning process.

The final output is a simple **Go HTTP server** with two endpoints that demonstrate real-world backend concepts in a beginner-friendly way.

---

## Technology Chosen
- **Language:** Go (Golang)

### Why Go?
I chose Go because it is a modern, statically typed language widely used for backend development, APIs, and cloud-native applications. I wanted to learn a language that emphasizes simplicity, performance, and clarity while being suitable for beginners.

### End Goal
To build and run a minimal Go HTTP server that responds to basic web requests.

---

## System Requirements
- **Operating System:** Linux / macOS / Windows  
- **Tools Required:**
  - Terminal (Bash, PowerShell, or CMD)
  - Visual Studio Code (recommended)
- **Language Runtime:** Go (Golang)
- **Version Control:** Git (optional but recommended)

---

## Installation & Setup Steps

### 1. Install Go
Download and install Go from the official website:  
https://go.dev/dl

---

### 2. Verify Installation
```bash
go version
Expected output:

text
Copy code
go version go1.x.x linux/amd64
3. Create Project Directory
bash
Copy code
mkdir prompt-powered-go
cd prompt-powered-go
4. Initialize Go Module
bash
Copy code
go mod init prompt-powered-go
This creates a go.mod file that manages project dependencies.

Minimal Working Example
Description
The example is a simple HTTP server with:

/ → Returns a greeting message

/health → Returns a health-check response

Code: main.go
go
Copy code
package main

import (
	"fmt"
	"log"
	"net/http"
)

func homeHandler(w http.ResponseWriter, r *http.Request) {
	fmt.Fprintln(w, "Hello, Go! 👋")
}

func healthHandler(w http.ResponseWriter, r *http.Request) {
	fmt.Fprintln(w, "OK")
}

func main() {
	http.HandleFunc("/", homeHandler)
	http.HandleFunc("/health", healthHandler)

	port := ":8080"
	log.Println("Server running on http://localhost" + port)
	log.Fatal(http.ListenAndServe(port, nil))
}
Run the Application
bash
Copy code
go run main.go
Expected Output
Browser: http://localhost:8080/ → Hello, Go! 👋

Browser: http://localhost:8080/health → OK

Code Explanation
package main: Declares this as an executable Go program.

import: Brings in standard libraries for formatting, logging, and HTTP handling.

homeHandler: Handles requests to the root (/) endpoint.

healthHandler: Handles requests to the /health endpoint.

http.HandleFunc: Maps URLs to handler functions.

http.ListenAndServe: Starts the HTTP server on port 8080.

AI Prompt Journal (Documentation Reference)
Prompt 1
Prompt Used:
Teach me Go like a beginner. How do I install Go and verify it works?

AI Help:
Provided installation steps and verification commands.

Evaluation:
Very helpful for initial setup and environment validation.

Prompt 2
Prompt Used:
Give me a minimal Go Hello World example and explain each line.

AI Help:
Explained Go syntax, package main, and the main() function.

Evaluation:
Helped me understand Go program structure clearly.

Prompt 3
Prompt Used:
Help me build a simple Go HTTP server with two routes.

AI Help:
Provided a working example using the net/http package.

Evaluation:
Extremely helpful for building a real, runnable project quickly.

Prompt 4
Prompt Used:
I’m getting go: command not found. How do I fix this?

AI Help:
Explained that Go was not installed and guided me through installation.

Evaluation:
AI was most useful during troubleshooting.

Common Errors & Fixes
Error: go: command not found
Cause: Go not installed or PATH not set

Fix: Install Go and restart the terminal

Error: bind: address already in use
Cause: Port 8080 already in use

Fix: Stop the running process or change the port number

Error: Server not responding
Cause: Server not running

Fix: Ensure go run main.go is still running in the terminal

References
Go Official Documentation: https://go.dev/doc

Go Tour: https://tour.golang.org

net/http Package Docs: https://pkg.go.dev/net/http

Conclusion
This project helped me understand Go fundamentals, backend routing concepts, and how AI tools can accelerate learning through guided explanations and troubleshooting. Using AI prompts significantly improved my learning speed and confidence while exploring a new programming language.