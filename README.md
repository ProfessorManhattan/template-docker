<!-- ⚠️ This README has been generated from the file(s) ".config/docs/blueprint-readme-app.md" ⚠️-->{{ load:.config/docs/readme/header.md }}
<div align="center">
  <a href="https://megabyte.space" title="Megabyte Labs homepage" target="_blank">
    <img alt="Homepage" src="https://img.shields.io/website?down_color=%23FF4136&down_message=Down&label=Homepage&logo=home-assistant&logoColor=white&up_color=%232ECC40&up_message=Up&url=https%3A%2F%2Fmegabyte.space&style=for-the-badge" />
  </a>
  <a href="https://github.com/megabyte-labs/template-docker/blob/master/docs/CONTRIBUTING.md" title="Learn about contributing" target="_blank">
    <img alt="Contributing" src="https://img.shields.io/badge/Contributing-Guide-0074D9?logo=github-sponsors&logoColor=white&style=for-the-badge" />
  </a>
  <a href="https://app.slack.com/client/T01ABCG4NK1/C01NN74H0LW/details/" title="Chat with us on Slack" target="_blank">
    <img alt="Slack" src="https://img.shields.io/badge/Slack-Chat-e01e5a?logo=slack&logoColor=white&style=for-the-badge" />
  </a>
  <a href="https://gitter.im/megabyte-labs/community" title="Chat with the community on Gitter" target="_blank">
    <img alt="Gitter" src="https://img.shields.io/gitter/room/megabyte-labs/community?logo=gitter&logoColor=white&style=for-the-badge" />
  </a>
  <a href="https://github.com/megabyte-labs/template-docker" title="GitHub mirror" target="_blank">
    <img alt="GitHub" src="https://img.shields.io/badge/Mirror-GitHub-333333?logo=github&style=for-the-badge" />
  </a>
  <a href="https://gitlab.com/megabyte-labs/templates/docker" title="GitLab repository" target="_blank">
    <img alt="GitLab" src="https://img.shields.io/badge/Repo-GitLab-fc6d26?logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgAQMAAABJtOi3AAAABlBMVEUAAAD///+l2Z/dAAAAAXRSTlMAQObYZgAAAHJJREFUCNdNxKENwzAQQNEfWU1ZPUF1cxR5lYxQqQMkLEsUdIxCM7PMkMgLGB6wopxkYvAeI0xdHkqXgCLL0Beiqy2CmUIdeYs+WioqVF9C6/RlZvblRNZD8etRuKe843KKkBPw2azX13r+rdvPctEaFi4NVzAN2FhJMQAAAABJRU5ErkJggg==&style=for-the-badge" />
  </a>
</div>
<br/>
<div align="center">
  <a title="Version: 8.11.0" href="https://github.com/megabyte-labs/template-docker" target="_blank">
    <img alt="Version: 8.11.0" src="https://img.shields.io/badge/version-8.11.0-blue.svg?logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgAQMAAABJtOi3AAAABlBMVEUAAAD///+l2Z/dAAAAAXRSTlMAQObYZgAAACNJREFUCNdjIACY//+BEp9hhM3hAzYQwoBIAqEDYQrCZLwAAGlFKxU1nF9cAAAAAElFTkSuQmCC&cacheSeconds=2592000&style=flat-square" />
  </a>
  <a title="GitLab build status" href="https://gitlab.com/megabyte-labs/templates/docker/-/commits/master" target="_blank">
    <img alt="Build status" src="https://img.shields.io/gitlab/pipeline-status/megabyte-labs/docker/app/template-docker?branch=master&label=build&logo=gitlab&logoColor=white&style=flat-square">
  </a>
  <a title="DockerHub image size" href="https://hub.docker.com/repository/docker/megabytelabs/template-docker" target="_blank">
    <img alt="Image size" src="https://img.shields.io/docker/image-size/megabytelabs/template-docker?logo=docker&sort=date&logoColor=white&style=flat-square">
  </a>
  <a title="DockerHub pulls" href="https://hub.docker.com/repository/docker/megabytelabs/template-docker" target="_blank">
    <img alt="Pulls" src="https://img.shields.io/docker/pulls/megabytelabs/template-docker?logo=docker&logoColor=white&style=flat-square">
  </a>
  <a title="DockerHub stars" href="https://hub.docker.com/repository/docker/megabytelabs/template-docker" target="_blank">
    <img alt="Stars" src="https://img.shields.io/docker/stars/megabytelabs/template-docker?logo=docker&logoColor=white&style=flat-square">
  </a>
  <a title="Documentation" href="https://megabyte.space/docs/docker" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg?logo=readthedocs&logoColor=white&style=flat-square" />
  </a>
  <a title="License: MIT" href="https://github.com/megabyte-labs/template-docker/blob/master/LICENSE" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-yellow.svg?logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgAQMAAABJtOi3AAAABlBMVEUAAAD///+l2Z/dAAAAAXRSTlMAQObYZgAAAHpJREFUCNdjYOD/wMDAUP+PgYHxhzwDA/MB5gMM7AwMDxj4GBgKGGQYGCyAEEgbMDDwAAWAwmk8958xpIOI5zKH2RmOyhxmZjguAiKmgIgtQOIYmFgCIp4AlaQ9OczGkJYCJEAGgI0CGwo2HmwR2Eqw5SBnNIAdBHYaAJb6KLM15W/CAAAAAElFTkSuQmCC&style=flat-square" />
  </a>
</div>

> </br><h4 align="center">**Boilerplate / starting point / instructions for creating a Dockerfile**</h4></br>

<a href="#table-of-contents" style="width:100%"><img style="width:100%" src="https://gitlab.com/megabyte-labs/assets/-/raw/master/png/aqua-divider.png" /></a>

## Table of Contents

- [Overview](#overview)
- [Docker Project Boilerplate Instructions](#docker-project-boilerplate-instructions)
  - [Multi-Stage Builds](#multi-stage-builds)
  - [DockerSlim Configuration](#dockerslim-configuration)
  - [Building the Dockerfile](#building-the-dockerfile)
  - [Testing the Dockerfile](#testing-the-dockerfile)
  - [Style Guide](#style-guide)
  - [Development Process Requirements](#development-process-requirements)
- [Automated README and Repository Build Settings](#automated-readme-and-repository-build-settings)
- [Requirements](#requirements)
  - [Development Requirements](#development-requirements)
  - [Building the Docker Container](#building-the-docker-container)
  - [Building a Slim Container](#building-a-slim-container)
  - [Build Tools](#build-tools)

<a href="#overview" style="width:100%"><img style="width:100%" src="https://gitlab.com/megabyte-labs/assets/-/raw/master/png/aqua-divider.png" /></a>

## Overview

This repository is the starting template for [Megabyte Labs](https://megabyte.space) Dockerfile repositories. **Read this document** before developing. There are important instructions on how to utilize pre-made build steps, details on compiling the repository from seed data, and instructions on how to implement test cases without reinventing the wheel.

<a href="#docker-project-boilerplate-instructions" style="width:100%"><img style="width:100%" src="https://gitlab.com/megabyte-labs/assets/-/raw/master/png/aqua-divider.png" /></a>

## Docker Project Boilerplate Instructions

All of the Docker containers we maintain are seperated into their own repository. In each repository, the common files shared across all our projects will be present along with:

1. The Dockerfile
2. A `test/` folder which will contain files used for testing the container after it is built
3. A `local/` folder which contains miscellaneous files. This is a good folder to store files that need to be copied to the Dockerfile during build time.

### Multi-Stage Builds

Whenever possible, a multi-stage build is preferred in any case where the production Docker container can be smaller in size. On top of that, whenever possible, [DockerSlim](https://github.com/docker-slim/docker-slim) should be used to create slim versions of the Docker containers. DockerSlim reduces the size of the image and improves the security of the image.

### DockerSlim Configuration

The DockerSlim configuration for each repository (if applicable) should be stored in the `package.json` file in the `blueprint` section. A configuration that reduced the size of the [ESLint CodeClimate image](https://gitlab.com/megabyte-labs/docker/codeclimate/eslint) by about 50% looks like this:

**`package.json`:**

```json
{
  ...
  "blueprint": {
    ...
    "dockerSlimCommand": {
      "codeclimate": "--http-probe=false --exec 'pnpm --help && pnpx --help && codeclimate-eslint' --mount \"./test/output-test:/code\" --workdir '/code' --preserve-path-file './local/paths.codeclimate.txt'",
      "eslint": "--http-probe=false --exec 'pnpm --help && pnpx --help && eslint --help' --preserve-path-file './local/paths.eslint.txt'"
    }
  }
}
```

You can see two different DockerSlim configurations are present in the snippet above. Each of the keys (`codeclimate` and `eslint`) correspond to build targets defined in the `Dockerfile`. The Dockerfile looks something like this:

```dockerfile
FROM node:17-alpine AS codeclimate

RUN ...

FROM codeclimate AS eslint

RUN ...
```

We have two build targets in this case because the ESLint CodeClimate project generates a [CodeClimate](https://docs.codeclimate.com/) engine and a standalone linter from the same Dockerfile. By matching up these keys, we open the doorway for scripted build and test tasks that significantly reduce the amount of code required.

### Building the Dockerfile

You can of course forget about the build targets and just add a regular Dockerfile - the command you would run would be the same in each case (`bash start.sh && task build` or `npm run build`). However, in almost all cases, you should leverage the system we created.

For each build target that you want to publish, create a file under `test/structure/<BUILD_TARGET_NAME>.yml`. Each of these files should be a basic [Google container-structure-test](https://github.com/GoogleContainerTools/container-structure-test). You can find examples of some in the [ESLint CodeClimate image](https://gitlab.com/megabyte-labs/docker/codeclimate/eslint) repository.

Now, when you run `task build`, the build script will determine which build targets we should tag and eventually publish by looking at the container-structure-test file names. The tests are also meant to provide some basic validation.

### Testing the Dockerfile

On top of the container-structure-test, there are a few other tests that will automatically run if the build targets are defined and certain conditions are met.

1. For each folder in the `test/` folder that has a title that starts with `output-`, the `task test` command will run both the regular and slim images using the following command:

```
docker run -v "<OUTPUT_FOLDER_PATH>:/work" -w /work <DOCKER_IMAGE>:<SLIM_OR_LATEST> .
```

The task will then compare the STDOUT of each command to make sure that the output of each container matches when run under similar conditions.

2. If any of the test folders contain a `.codeclimate.yml` file, then the CodeClimate CLI will run in those folders. It is only important to include this type of test if you are building a CodeClimate engine.

3. To simulate how the images will run in the GitLab CI environment, you can add a definition in `.gitlab-ci.yml` that begins with `integration:`. For each definition, a local instance of GitLab Runner will simulate the defined "integration" test. This test could look something like this:

**`.gitlab-ci.yml`**

```yml
---
integration:codeclimate:
  image: megabytelabs/codeclimate:slim
  script:
    - bash ...
    - echo "test routine here"
```

As long as GitLab Runner does not exit with an error code, the test passes.

### Style Guide

All of our Dockerfile repositories should be similar to other Dockerfile projects that are in the same group. The groups are:

1. [Ansible Molecule](https://gitlab.com/megabyte-labs/docker/ansible-molecule) containers
2. [Apps](https://gitlab.com/megabyte-labs/docker/app)
3. [CI Pipeline](https://gitlab.com/megabyte-labs/docker/ci-pipeline)
4. [CodeClimate](https://gitlab.com/megabyte-labs/docker/codeclimate)
5. Docker Compose - N/A
6. [Software](https://gitlab.com/megabyte-labs/docker/software)

We use Hadolint to lint the Dockerfiles. You can lint the Dockerfile by running `task lint:docker`.

### Development Process Requirements

The following outlines the process you should follow when designing a Dockerfile for the [Megabyte Labs](https://megabyte.space) eco-system:

1. Model your Dockerfile and repository based on a repository that is in the same group - keep the labels, make note of how the `ENTRYPOINT` and `CMD` definitions are defined, etc.
2. Ensure you can build the Docker image(s) with the `task build` command
3. Ensure the tests pass by running `task test`
4. Ensure the Dockerfile passes the lint tests by running `task lint:docker` and `task lint:all`
5. Add repository blueprint data. This involves looking at a similar repository's `package.json` file in the `blueprint` section. Create a similar `blueprint` section in your repository. On top of that, replace the `docs/partials/guide.md` file with some documentation written in markdown. This file will be used to generate the `README.md`. Start the first heading off with `## Documentation Title Here`.
6. Trigger the repository to recompile itself now that you added the `blueprint` data and some custom, relevant doumentation by running `task update`.
7. When you are ready, create a new PR branch and commit the code by running `git commit` - this will trigger an interactive process that ensures the files are linted and that your commit comment is in the proper format.
8. Push your branch and open a PR once the CI/CD pipeline passes

<a href="#automated-readme-and-repository-build-settings" style="width:100%"><img style="width:100%" src="https://gitlab.com/megabyte-labs/assets/-/raw/master/png/aqua-divider.png" /></a>

## Automated README and Repository Build Settings

We automate as much as possible. This allows us to create polished open source repositories complete with the ideal configuration files, ample documentation, and convienience features like `.vscode/` settings and `.devcontainer/` environment definitions. You should expect to see the content below also show up after you have customized your `docs/partials/guide.md` and have run `task update`.

<a href="#requirements" style="width:100%"><img style="width:100%" src="https://gitlab.com/megabyte-labs/assets/-/raw/master/png/aqua-divider.png" /></a>

## Requirements

- **[Docker](https://gitlab.com/megabyte-labs/ansible-roles/docker)**

### Development Requirements

- **[DockerSlim](repository.project.dockerslim)** - Used for generating compact, secure images
- **[jq](repository.project.jq)** - Used for interacting with JSON
- **[Node.js](repository.project.node)** (_>=14.18_) - Utilized to add development features like a pre-commit hook and maintenance tasks
- _Many more_ requirements that are _dynamically installed_ as they are needed by our `Taskfile.yml` via our custom [go-task/task](https://github.com/go-task/task) fork named **[Bodega](https://github.com/ProfessorManhattan/Bodega)**

If you choose to utilize the development tools provided by this project then at some point you will have to run `bash start.sh` (or `npm i` which calls `bash start.sh` after it is done). The `start.sh` script will attempt to automatically install any requirements (without sudo) that are not already present on your build system to the user's `~/.local/bin` folder. The `start.sh` script also takes care of other tasks such as generating the documentation by calling tasks defined in the `Taskfile.yml`. For more details on how the optional requirements are used and set up, check out the [CONTRIBUTING.md](https://gitlab.com/megabyte-labs/docker/app/template-docker/-/blob/master/docs/CONTRIBUTING.md) guide.

When you are ready to start development, run `task --menu` to open an interactive dialog that will help you understand what build commands we have already engineered for you.

### Building the Docker Container

You may have a use case that requires some modifications to our Docker image. After you make changes to the Dockerfile, you can upload your custom container to [Docker Hub](website.dockerhub) using the following code:

```shell
export DOCKERHUB_USERNAME=Your_DockerHub_Username_Here
export DOCKERHUB_PASSWORD=Your_DockerHub_Password_Here
docker login -u "$DOCKERHUB_USERNAME" -p "$DOCKERHUB_PASSWORD" docker.io
docker build --pull -t "$DOCKERHUB_USERNAME/template-docker:latest" .
docker push "$DOCKERHUB_USERNAME/template-docker:latest"
```

After setting your DockerHub username and password, the commands above will build the Docker image and upload it to [Docker Hub](https://hub.docker.com/) where it will be publicly accessible. You can see this logic being implemented as a [GitLab CI task here](repository.link.dockerhub_ci_task). This GitLab CI task works in conjunction with the `.gitlab-ci.yml` file in the root of this repository.

### Building a Slim Container

Some of our repositories support creating a slim build via [DockerSlim](https://gitlab.com/megabyte-labs/ansible-roles/dockerslim). According to [DockerSlim's GitHub page](https://github.com/docker-slim/docker-slim), slimming down containers reduces the final image size and improves the security of the image by reducing the attack surface. It makes sense to create a slim build for anything that supports it, including Alpine images. On their GitHub page, they report that some images can be reduced in size by up to 448.76X. This means that if your image is naturally **700MB** then it **can be reduced to 1.56MB**! It works by removing everything that is unnecessary in the container image.

As a convenience feature, we include a command defined in `package.json` that should build the slim image. Just run `task docker:build` after running `npm i` (or `bash start.sh` if you do not have `Node.js` installed) in the root of this repository to build both the `latest` and `slim` builds.

To build and publish a `slim` Dockerfile to Docker Hub manually, you can use the following as a starting point:

```shell
export DOCKERHUB_USERNAME=Your_DockerHub_Username_Here
export DOCKERHUB_PASSWORD=Your_DockerHub_Password_Here
docker login -u "$DOCKERHUB_USERNAME" -p "$DOCKERHUB_PASSWORD" docker.io
docker build -t "$DOCKERHUB_USERNAME/template-docker:latest" .
docker-slim build --tag $DOCKERHUB_USERNAME/template-docker:slim {{#if (eq (typeOf dockerSlimCommand) "string")}}dockerSlimCommand}}{{/if{{#if (not (eq (typeOf dockerSlimCommand) "string"))}}dockerSlimCommand[slug]}}{{/if $DOCKERHUB_USERNAME/template-docker:latest
docker push "$DOCKERHUB_USERNAME/template-docker:slim"
```

It may be possible to modify the DockerSlim command above to fix an issue or reduce the footprint even more than our command. You can modify the slim build command inline in the `package.json` file under `blueprint.dockerSlimCommand`. Some of our repositories have multiple build targets in the `Dockerfile` so those repositories will have multiple `dockerSlimCommands`.

If you come up with an improvement, please do [open a pull request](repository.group.dockerCodeClimate/template-docker/-/issues/new). And again, make sure you replace `DOCKERHUB_USERNAME` and `DOCKERHUB_PASSWORD` in the snippet above with your Docker Hub username and password. The commands in the snippet above will build the slim Docker image and upload it to [Docker Hub](https://hub.docker.com/) where it will be publicly accessible.

### Build Tools

You might notice that we have a lot of extra files considering that this repository basically boils down to a single Dockerfile. These extra files are meant to make team development easier, predictable, and enjoyable. If you have a recent version of [Node.js](repository.project.node) installed, you can get started using our build tools by running `npm i` (or by running `bash start.sh` if you do not currently have Node.js installed) in the root of this repository. After that, you can run `task --list` to see a list of the available development features. Alternatively, you can run `task --menu` to view an interactive menu that will guide you through the development process.

_Note:_ We use a custom-built version of [go-task/task](https://github.com/go-task/task) so if you already have it installed then you should either replace it with our version or use a different bin name for `task`.

For more details, check out the [CONTRIBUTING.md](https://gitlab.com/megabyte-labs/docker/app/template-docker/-/blob/master/CONTRIBUTING.md) file.

{{ load:.config/docs/readme/contributing-details.md }}
{{ load:.config/docs/readme/license.md }}
