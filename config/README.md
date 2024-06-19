# Customizations for acm-config (a.k.a. ".arkcase")

This project houses files that are meant to be deployed directly into an ArkCase configuration set. The files are treated as Java resources, and thus the final artifact will end up being a JAR file. These configurations are meant to provide any necessary groundwork from the sibling *extension* project.

On deployment, the extension's *profile* is named ***custom***. This is important because it allows the selective override of some configuration files (as documented elsewhere) by just providing a YAML file (or somesuch) with the ***\*-custom.\**** suffix, like so:

```
src/
└── main
    └── resources
        └── acm
            ├── accessControlRules.json
            ├── acm-config-server-repo
            │   ├── arkcase-custom.yaml
            │   ├── arkcase-portal-custom.yaml
            │   ├── branding
            │   │   ├── banner-portal-custom.png
            │   │   ├── email-logo-custom.png
            │   │   ├── header-logo-custom.png
            │   │   ├── header-logo-portal-custom.png
            │   │   ├── login-logo-custom.png
            │   │   ├── login-logo-portal-custom.png
            │   │   ├── mobile-banner-portal-custom.png
            │   │   ├── portal-custom.css
            │   │   └── regions-custom.png
            │   ├── labels
            │   │   ├── document-details-en-custom.yaml
            │   │   ├── external-portal-en-custom.yaml
            │   │   └── tasks-en-custom.yaml
            │   ├── lookups
            │   │   └── lookups-custom.yaml
            │   └── rules
            │       └── drools-task-rules-custom.xlsx
            └── acmSequenceConfiguration.json
```

Note that you can also include complete file replacements (like ***accessControlRules.json*** and ***acmSequenceConfiguration.json***, above) if you want to completely override files from the original configuration set.

The value of the ***\*-custom.\**** approach is that it allows developers to not have to copy entire configuration files, and instead just override specific portions as required by the extension.

Still, there are some files that can't be augmented in this manner, and as a result still must be overridden completely (i.e. the json files, above).