# Specification

## Common

| CATEGORY | NAME                            | ADDED IN | EXAMPLE             | DESC                                                                                   |
|----------|---------------------------------|----------|---------------------|----------------------------------------------------------------------------------------|
| common   | `NCI`                           | 1.0.0    | true                | can be used to check if normalized variables are present                               |
| common   | `NCI_VERSION`                   | 1.0.0    | 1.0.0               | the version of the NCI spec that is used, newer versions may add additional fields     |
| common   | `NCI_SERVICE_NAME`              | 1.0.0    | GitHub Actions      | commercial name of the used ci platform (e.g. GitLab CI, Travis CI, CircleCI, Jenkins) |
| common   | `NCI_SERVICE_SLUG`              | 1.0.0    | github-actions      | commercial name of the used ci platform as slug                                        |

## Worker

| CATEGORY | NAME                            | ADDED IN | EXAMPLE             | DESC                                                                                   |
|----------|---------------------------------|----------|---------------------|----------------------------------------------------------------------------------------|
| worker   | `NCI_WORKER_ID`                 | 1.0.0    | 12270837            | unique id of the ci worker                                                             |
| worker   | `NCI_WORKER_NAME`               | 1.0.0    | 4-blue.worker.local | human readable name of the ci worker                                                   |
| worker   | `NCI_WORKER_VERSION`            | 1.0.0    | 6.10.0              | version of the ci worker                                                               |
| worker   | `NCI_WORKER_ARCH`               | 1.0.0    | linux/amd64         | arch of the ci worker                                                                  |

## Pipeline

| CATEGORY | NAME                            | ADDED IN | EXAMPLE             | DESC                                                                                   |
|----------|---------------------------------|----------|---------------------|----------------------------------------------------------------------------------------|
| pipeline | `NCI_PIPELINE_TRIGGER`          | 1.0.0    | push                | pipeline trigger (manual/push/trigger/api/schedule/pull_request/build)                 |
| pipeline | `NCI_PIPELINE_STAGE_NAME`       | 1.0.0    | build               | stage name                                                                             |
| pipeline | `NCI_PIPELINE_STAGE_SLUG`       | 1.0.0    | build               | stage name as slug                                                                     |
| pipeline | `NCI_PIPELINE_JOB_NAME`         | 1.0.0    | go-build            | job name                                                                               |
| pipeline | `NCI_PIPELINE_JOB_SLUG`         | 1.0.0    | go-build            | job name as slug                                                                       |
| pipeline | `NCI_PIPELINE_PULL_REQUEST_ID`* | 1.0.0    | 51                  | arch of the ci worker                                                                  |

## Project

| CATEGORY | NAME                            | ADDED IN | EXAMPLE             | DESC                                                                               |
|----------|---------------------------------|----------|---------------------|------------------------------------------------------------------------------------|
| project  | `NCI_PROJECT_ID`                | 1.0.0    | 1000                | unique project id                                                                  |
| project  | `NCI_PROJECT_NAME`              | 1.0.0    | my-project          | project name                                                                       |
| project  | `NCI_PROJECT_PATH`              | 1.0.0    | org/my-project      | project namespace with the project name                                            |
| project  | `NCI_PROJECT_SLUG`              | 1.0.0    | org-my-project      | project name                                                                       |
| project  | `NCI_PROJECT_DESCRIPTION`       | 1.0.0    | awesome project     | project description                                                                |
| project  | `NCI_PROJECT_TOPICS`            | 1.0.0    | hacktoberfest       | project topics                                                                     |
| project  | `NCI_PROJECT_ISSUE_URL`         | 1.0.0    | http://jira.local/  | project name                                                                       |
| project  | `NCI_PROJECT_STARGAZERS`        | 1.0.0    | 204                 | project name                                                                       |
| project  | `NCI_PROJECT_FORKS`             | 1.0.0    | 21                  | project name                                                                       |
| project  | `NCI_PROJECT_DIR`               | 1.0.0    | /my-project         | project dir                                                                        |

## Repository


| CATEGORY   | NAME                                 | ADDED IN | EXAMPLE                                  | DESC                             |
|------------|--------------------------------------|----------|------------------------------------------|----------------------------------|
| repository | `NCI_REPOSITORY_KIND`                | 1.0.0    | git                                      | version control system type      |
| repository | `NCI_REPOSITORY_REMOTE`              | 1.0.0    | https://github.com/org/my-project.git    | remote url (or local)            |
| repository | `NCI_COMMIT_REF_TYPE`                | 1.0.0    | branch                                   | reference type                   |
| repository | `NCI_COMMIT_REF_NAME`                | 1.0.0    | main                                     | human readable ref name          |
| repository | `NCI_COMMIT_REF_PATH`                | 1.0.0    | branch/main                              | composition of ref type and name |
| repository | `NCI_COMMIT_REF_SLUG`                | 1.0.0    | branch-main                              | slug of the vcs ref              |
| repository | `NCI_COMMIT_REF_VCS`                 | 1.0.0    | refs/heads/main                          | native vcs ref                   |
| repository | `NCI_COMMIT_REF_RELEASE`             | 1.0.0    | main                                     | suggested release name           |
| repository | `NCI_COMMIT_SHA`                     | 1.0.0    | 520951f                                  | short commit hash                |
| repository | `NCI_COMMIT_SHA_SHORT`               | 1.0.0    | 520951fbe7bf1b2999d874b58930863c529d14cb | commit hash                      |
| repository | `NCI_COMMIT_AUTHOR_NAME`             | 1.0.0    | Name                                     | author email                     |
| repository | `NCI_COMMIT_AUTHOR_EMAIL`            | 1.0.0    | name@example.com                         | author email                     |
| repository | `NCI_COMMIT_COMMITTER_NAME`          | 1.0.0    | name                                     | committer name                   |
| repository | `NCI_COMMIT_COMMITTER_EMAIL`         | 1.0.0    | name@example.com                         | committer email                  |
| repository | `NCI_COMMIT_TITLE`                   | 1.0.0    | feat: add new feature                    | commit title                     |
| repository | `NCI_COMMIT_DESCRIPTION`             | 1.0.0    | added a new feature                      | commit description               |
| repository | `NCI_COMMIT_COUNT`                   | 1.0.0    | 1341                                     | total commit count               |

## Control

| CATEGORY   | NAME                | ADDED IN | EXAMPLE | DESC                  |
|------------|---------------------|----------|---------|-----------------------|
| repository | `NCI_DEPLOY_FREEZE` | 1.0.0    | false   | deploy freeze active? |

## Package Registries

| CATEGORY    | NAME                               | ADDED IN | EXAMPLE        | DESC                          |
|-------------|------------------------------------|----------|----------------|-------------------------------|
| pkgregistry | `NCI_CONTAINERREGISTRY_HOST`       | 1.0.0    | docker.io      | container registry host       |
| pkgregistry | `NCI_CONTAINERREGISTRY_USERNAME`   | 1.0.0    | my-user        | container registry username   |
| pkgregistry | `NCI_CONTAINERREGISTRY_PASSWORD`   | 1.0.0    | my-pw          | container registry password   |
| pkgregistry | `NCI_CONTAINERREGISTRY_REPOSITORY` | 1.0.0    | org/my-project | container registry repository |
| pkgregistry | `NCI_CONTAINERREGISTRY_TAG`        | 1.0.0    | latest         | container registry host       |
