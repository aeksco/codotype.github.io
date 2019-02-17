# Codotype Generator Directory Structure

Codotype Generators require a specific directory structure to function correctly. The benefit of this structure approach is to effectively relieve generator developers of the burdens of decision making during the authoring process.

## General Structure

The general directory structure of a generator is as follows:

```
├── generator
│   ├── index.js
│   └── component
│       ├── index.js
│       └── templates
│           └── app.js
├── LICENSE
├── meta.json
├── package.json
└── README.md
```

A breakdown of individual files and structures is outlined below.

## README.md

The `README.md` file is required for a Codotype generator. This is where you one outlines the features of a generator and some documentation about the code that it produces. The `README.md` file is rendered in the Codotype web interface.

## package.json

The `package.json` file is required so a Codotype generator may be installed as a dependency with `npm install`. It dictates the requisite `@codotype` dependencies for the generator, and any additional third-party dependencies upon which that generator depends.

## LICENSE

A `LICENSE` file is required for both your generator, as well as the codebase produced by it.

## meta.json

The `meta.json` file is arguably the important file in the generator's definition - it dictates the end-user experience of using a generator and defines all the requisite metadata that's passed to the Codotype web interface and runtime. A breakdown of the file is as follows:

- `id` - unique ID for the generator
- `label` - short label for the generator
- `description` - brief description of the generator
- `icon` - URL to the generator's icon
- `tech_tags` - an array of strings describing the tech used in the generator
- `type_tags` - describes the type of codebase produced by this generator
- `self_configuring` - whether or not the generator requires a Blueprint to operate
- `project_path` - the name of the directory for the generator's output
- `github_url` - the slug of the GitHub repository for this generator
- `version` - the current version of the generator
- `official` - if the generator is published by codotype
- `experience` - an optional tag detailing the level of experience required to use the code produced by the generator
- `option_groups` - an array of `OptionGroup` objects that expose additional configuration provided by the generator