# Repository readme template

The purpose of a repository's readme is to quickstart developers who are unfamiliar with it or rusty.

The target audience is developers, so internal, business-oriented, product documentation belongs elsewhere.

A repository may contain one or more distinct product, where a product is an independently startable application or service - or an independently publishable library. Generally each product warrants its own readme. A multiproduct repository may have a top-level readme that links to the per-product readmes.

In the following template, placeholders are in `{curly braces}`. Not all sections may be applicable to every product implementation.

<hr/>

# {official name of the product}

aka. {colloquial nicknames of the product}

{summary description of the product}

## Links

- [homepage]({url-of-homepage})
- [documentation]({url-of-product-documentation})
- [roadmap]({url-of-roadmap})
- [discussion forum]({url-of-discussion-forum})
- [issue tracker]({url-of-issue-tracker})
- [pipeline]({url-of-pipeline})
- [repository]({url-of-repository})

## Experts

- {name of person or team} ({nature of expertise, e.g. "product" or "implementation"})

## Domain

- **{term}** - {definition}

## History

{history of this product, for context}

## Features

{a breakdown of the major features or responsibilities}

## Consumers

- **{consumer type}** - {the consumer's general use case}

## Monitoring

{description of monitoring and alerting strategy}

## Versioning

{description of versioning and deprectation strategy}

## Instances and external dependencies

- **{instance name}**
    - uses:
        - {use case}
    - base URIs:
        - {instance base URI}
    - monitoring:
        - [{monitoring venue name}]({monitoring-venue-uri})
    - external dependencies:
        - {dependency name}: {dependency instance}

## Folder organization

{high-level map of important folders in the repository}

## Layers and modules

{a dependency graph of modules and layers implemented in this repository}

## Execution entrypoints

{a list of entrypoints for starting the application and processing requests}

## Lava layers

{identification of lava layers, and their context or history}

## Engineering conventions

{notable conventions followed in this repository}

## Feature development workflow

### One-time workstation setup

{steps or checklist for one-time workstation setup, e.g. runtimes, OS features, global tools and editors, extensions, port configuration}

### Post-checkout setup

{steps a developer may need to perform after checking out a branch, e.g. restoring package dependencies, configuring environment variables}

### Building

{steps to build}

### Running tests

{categorizations of, and steps to run, automated tests, including linting}

### Starting an instance

{steps to start an instance}

### Consuming an instance

{steps to consume an instance, esp. a healthcheck}

### Debugging

{steps to debug}

### {Unique feature development task}

{steps}

### Packaging

{steps to generate a deployment package}

### Branching and commits

{guidelines for branch naming, reserved branches, and commit messages}

### Integration and deployment

{workflow for PRs, QA, sign-off, integration, deployment, monitoring}

### Rolling back

{guidelines and steps for reverting or rolling back}

## See also

- [{reference title}]({url-to-reference})
