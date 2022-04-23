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

## Automated README and Repository Build Settings

We automate as much as possible. This allows us to create polished open source repositories complete with the ideal configuration files, ample documentation, and convienience features like `.vscode/` settings and `.devcontainer/` environment definitions. You should expect to see the content below also show up after you have customized your `docs/partials/guide.md` and have run `task update`.
