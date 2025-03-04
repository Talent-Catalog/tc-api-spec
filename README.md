# Talent Catalog API Specification

This repository contains the **OpenAPI specification** for the **Talent Catalog API**.


## Steps to View the API Specification with ReDoc

### Step 1: Install Node.js and npm

If you don't already have Node.js installed, you need to install it first. Installing Node.js also 
installs npm (Node Package Manager), which is required to install tools like `@redocly/cli`.

1. Download the latest version of Node.js from the [Node.js website](https://nodejs.org/).
2. Follow the installation instructions for your platform (Windows, macOS, Linux).

To verify installation, run the following commands:

```bash
node -v
npm -v
```

Both commands should display version numbers if the installation was successful.




### Step 2: Install the OpenAPI CLI Tool

To view the OpenAPI specification, install the `@redocly/cli` tool, which is a command-line utility 
provided by ReDocly.

Install it globally using npm:

```bash
npm install -g @redocly/cli
```

This installs the OpenAPI CLI tool globally on your system, allowing you to use it from any directory.



### Step 3: Preview the API Specification Using ReDoc

To preview the API documentation rendered with ReDoc, start a local server:

```bash
openapi preview-docs ./openapi.yaml --port 9090
```

This command will start a local web server where you can view a rendered version of the API 
documentation.



