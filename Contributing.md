# Contributing

Everybody is welcome to extend and add their information to this document. The only strict requirements are [getting a review](#reviews) and [adhering to this document structure](#structure-of-the-document).

## Structure of the document

`src/current` folder shall contain documentation about the current state of EO-CM. It shall strictly contain already implemented information.

`src/proposals` folder shall contain descriptions of new proposals on architecture changes, architecturally impacting MRs, improvement.


## Reviews

When extending either the `current` folder, please invite design leads to review the document (gerrit group: HoneyLeads). For adding proposals, feel 
free to throw in any 
stuff it can be a collection place of half-baked stuff.


## Information pieces that could be captured

The descriptions below are suggestions on how to capture the various aspects. Adhering to this format is not mandatory, but it is a good to have, since it provides a sort of consistency across the various documents.

### Diagrams

Main usecase flows through the system as sequence diagrams. It's not necessary to document each and every single usecase flow, if multiple flows are taking the same paths through the components in the architecture, then a single diagram suffices.

For depicting component relations both on a application and on a service level the [c4 model](https://c4model.com/) shall be used. This can be done with using the [C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML) library alongside [Plantuml](#creating-plantuml-images).

### Design rules

Design rules, both for overall and for component specific workflows shall be captured in the design rules. If it's a coding related design rule then it's a good idea if code examples and example commits are provided along with the description of the design rule.

### Development/CI Flows

Explanations on what kind of flows a particular piece of software goes through when it's getting contributed into various repositories and how it gets delivered to the customer.

## Adding new pages

All of the content shall go into the `src` directory of this repository.
Each page should have a top level (`# Page title`) heading in the document.
Also please make sure that it's reachable through a link from an other page, the root page being the `Readme.md` of this document.

## Creating PlantUML images

[PlantUML](https://plantuml.com/) is a markup language and render tool that can be used to generate UML and UML-like diagrams. It should be used as the primary tool for creating diagrams since the markup language is easily version controllable.

Creating such a diagram consist of the following steps:

1. create a `.puml` file somewhere in the `src` directory
2. run `./bob/bob build` in the ro
3. ot folder of this repository - If this is the first time executing this command, see [this guide]
   (#setting-up-the-image-builder)
3. Add the generated image references to your markdown documentation.

### Types of diagrams to be produced

### Setting up the image builder

The image builder tool is packaged as a docker image and uses the bob tool from ADP to provide an execution environment for it.

#### Docker

Have a docker client and an associated docker daemon so that the image builder executable can run.

#### Get Bob submodule

To get bob:

Run:
`git submodule update --init --recursive`

This will add the bob submodule to the repository, and it can

Bob is a build tool that can be used to execute the various docker containers in the current context.
For more detailed descriptions on how to use it, see: [Bob user Guide](https://gerrit.ericsson.se/plugins/gitiles/adp-cicd/bob/+/refs/heads/master/USER_GUIDE_2.0.md#Getting_started)
