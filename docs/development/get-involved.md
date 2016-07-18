---
layout: page
title: Get Involved
subtitle: "Get Involved with Samsara's development"
nav: documentation
---


If you wish to get involved with the Samsara's development, follow these steps.

   - Read the `HELP-US.md` (in the project's root) to see what
     contributions we are looking for.
   - Check the list of [open issues](https://github.com/samsara/samsara/issues)
     on Github.
   - If you have found something you wish contribute or you have
     something else in mind speak to us by writing a mail to: `samsara
     [dot] systems+info at gmail [dot] com`
   - Issues might be poorly described or with no description at all,
     talk to us, ask us questions, ask us more details.
   - We will invite you to our Slack channel where you can talk with
     the authors and other contributors and propose your suggestions.
   - Then try to run the system following the [Quick Start guide](/docs/quick-start)
   - Then try to build the system following these in this guide.


## The project structure

This single project contains all sub-systems organized with
their own projects.

   * `clients/` - Here are the clients libraries in various
     languages to send events to Samsara.
     * `clojure/` - The Clojure's client
     * `ios/` - The Swift iOS client
     * `logger/` - A Java Log4j, Logback, Slf4j logger to push log
       lines as events.
   * `ingestion-api/` - The REST api endpoint where the events
     are sent to.
   * `core/` - The engine library for processing streams.
   * `moebius/` - The stream processing functions abstractions
   * `utils/` - Common utilities used in other projects
   * `qanal/` - The component which indexes the processed events
     into ElasticSearch
   * `docker-images/` - The docker projects to build all third-party components
   * `deployments/` - Deployment descriptors and script to deploy the Samsara.

There are many inter-dependencies between these projects, but they all
follow a single version schema which is controlled by `samsara.version` file.
If you wish to build your local dependencies follow these instructions.

## Build Samsara.

To build all Samsara projects and their dependencies follow:

``` bash
git clone https://github.com/samsara/samsara.git
cd samsara
./bin/build-all-projects.sh
```

This will build all the dependencies and install them in your local maven
repo (`~/.m2/repository/`).
