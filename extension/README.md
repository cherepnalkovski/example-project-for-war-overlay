# Code extensions for ArkCase

This project houses files that are meant to be used to build an actual code extension to ArkCase. It's meant to work in tandem with any configuration extensions from the sibling *config* project, and produce any requisite JAR files that can be deployed alongside ArkCase.

The structure is that of a normal Java JAR project, and is expected to produce a singular JAR file. However, if additional libraries must also be deployed alongside, they can also be declared in the POM for this project, using either ***compile*** or ***runtime*** scopes, in order to have the build process include them automatically in the resulting deployable bundle.