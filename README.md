# Talent Catalog API Specification

This repository contains the **OpenAPI specification** for the **Talent Catalog API**.

> **Note**: In addition to serving as the canonical API specification, this repository generates a 
> Maven artefact containing the generated API models and controllers. This artefact is published to 
> Maven Central and is used as a dependency by the Talent Catalog service and core projects.


## Viewing the API Specification with ReDoc

### 1. Install Node.js and npm

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

### 2. Install the OpenAPI CLI Tool

To view the OpenAPI specification, install the `@redocly/cli` tool, which is a command-line utility 
provided by ReDocly.

Install it globally using npm:

```bash
npm install -g @redocly/cli
```

This installs the OpenAPI CLI tool globally on your system, allowing you to use it from any directory.

### 3. Preview the API Specification Using ReDoc

To preview the API documentation rendered with ReDoc, start a local server:

```bash
openapi preview-docs ./openapi.yaml --port 9090
```

This command will start a local web server where you can view a rendered version of the API 
documentation.


## Publishing the API as an Artefact to Maven Central

Developers working on the API specification are expected to publish the generated code as a Maven 
artefact. Follow these steps to publish to Maven Central:

### 1. Prepare Your Environment

- **Sonatype account and artefact signing:** To publish artifacts to Maven Central, please contact 
  a TC core team member to obtain the necessary Sonatype and GPG credentials for the Talent Catalog 
  group ID (`org.tctalent`).

### 2. Set the Project Version

- For **stable releases**, update the version in `build.gradle` to a non-SNAPSHOT version (e.g., 
  `1.0.1`).
- For **ongoing development**, you may use a SNAPSHOT version (e.g., `1.0.2-SNAPSHOT`), which should 
  be published to Maven locally for iterative development.

### 3. Generate and Package the Artifact

To generate and publish the artefact on Maven Central, run the following commands:

```bash
./gradlew clean openApiGenerate
./gradlew publish
```

This compiles the generated code and packages it into a JAR that includes the API models and 
controllers and publishes it to Sonatype (Maven Central) for verification.

If you are iterating locally on spec changes, do not `publish`. Instead,
you should use:

```bash
./gradlew publishToMavenLocal
```

This will publish the artifact to your local Maven repository, allowing the service project to pick 
up changes quickly.

### 4. Promote the Artefact to Maven Central

After uploading the API artifact to Sonatype, you must log in to the 
[Maven Central Repository Manager](https://central.sonatype.com/) using your Sonatype account. From 
there, you will need to:

- **Review the artefact deployment:** Verify that your artifact has been correctly uploaded and 
  verified.
- **Publish the artefact to Maven Central:** Once everything is approved, publish the artefact to 
  promote it to Maven Central.

*Note:* This manual promotion to Maven Central may be automated in future updates to the CI/CID 
pipeline.
