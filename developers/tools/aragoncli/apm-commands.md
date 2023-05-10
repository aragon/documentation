# APM commands

{% hint style="info" %}
The `aragon apm` commands are the easiest way to <mark style="color:blue;">manage aragonPM repositories</mark>.
{% endhint %}

## aragon apm packages <a href="#aragon-apm-packages" id="aragon-apm-packages"></a>

Lists all the packages in a apm registry.

```
aragon apm packages [apmRegistry]
```

* `apmRegistry`: The registry to inspect. Defaults to `aragonpm.eth`.

## aragon apm info <a href="#aragon-apm-info" id="aragon-apm-info"></a>

Shows information about a repository.

```
aragon apm info <apmRepo> [apmRepoVersion]
```

* `apmRepo`: Name of the APM repository.
* `apmRepoVersion`: Version of the repo. Defaults to `latest`.

## aragon apm publish <a href="#aragon-apm-publish" id="aragon-apm-publish"></a>

The `aragon apm publish` command publishes a new version to the aragonPM repo. Check the [How to publish an Aragon App to aragonPM](../guides/publish-to-aragonpm.md) guide to learn more about the publish workflow.

```
aragon apm publish <bump> [contract]
```

* `bump`: Type of bump (major, minor or patch) or version number.
* `contract`: (optional) The address or name of the contract to publish in this version. If it isn't provided, it will default to the contract specified in the `arapp.json` file.

{% hint style="warning" %}
**Note**\
Changes to the contract can only be published with a major version bump. Minor and patch versions are only for frontend changes.
{% endhint %}

If a minor or patch version is being published then the command can be run with the `--only-content` flag which will skip compiling the contracts.

You can target a particular directory to publish, using `--files`. By default we only include `artifact.json`, `code.sol` and `manifest.json`.

We always publish apps with:

```
aragon apm publish <version> --environment <environment> --files app/build
```

The command has the following parameters:

* `--only-content`: For minor and patch upgrades; whether to skip contract compilation, deployment and contract artifact generation.
* `--only-artifacts`: Whether just generate artifacts file without publishing.
* `--init`: Arguments to be passed to contract constructor on deploy. Need to be separated by a space. The `@ARAGON_ENS` alias can be used and it will be replaced by the address of the ENS registry in the devchain.
* `--provider`: The provider where the files of the package will be published to. Defaults to `ipfs`.
* `--files`: The path to the files that will be published. Defaults to the current directory.
* `--ignore`: A gitignore pattern of files to ignore. Specify multiple times to add multiple patterns. Defaults to just the `node_modules` directory.
* `--publish-dir`: The path to the directory where all the files and generated artifacts will be copied to before publishing. If it is not specified, it will create a temporary directory.
* `--build`: A flag to specify whether the webapp should be built while publishing, running the script specified in `build-script` of `package.json`. Defaults to `true`.
* `--build-script`: The name of the NPM script in your app that will be used for building the webapp.
* `--prepublish`: A flag to specify whether to run a prepublish script specified in `prepublish-script` of `package.json`. Defaults to `true`.
* `--prepublish-script`: The name of the NPM script in your app that will be run before publishing the app. Defaults to `prepublishOnly`.
* `--http`: The URI for the HTTP server that will be serving your app files (e.g. localhost:1234). See [instructions on running from HTTP ](apm-commands.md)for more information.
* `--http-served-from`: Path to the directory that the HTTP server exposes (e.g. ./dist). Some artifacts are generated and placed in this directory during the publishing process of your app.
* `--ipfs-check`: Whether to have start IPFS if not started. Defaults to `true`.
* `--reuse`: Whether to reuse the previous version contract and skip deployment on non-major versions. Defaults to `false`.
* `--propagate-content`: Whether to propagate the content once published. Defaults to `true`.
* `--skip-confirmation`: Whether to skip the confirmation step. Defaults to `false`.

## aragon apm extract-functions <a href="#aragon-apm-extract-functions" id="aragon-apm-extract-functions"></a>

Extract function information from a Solidity file.

```
aragon apm extract-functions [contract]
```

* `contract`: Path to the Solidity file to extract functions from.

Options:

* `--output`: Path of the directory where the output file will be saved to.

## aragon apm versions <a href="#aragon-apm-versions" id="aragon-apm-versions"></a>

Shows all the previously published versions of a given repository.

```
aragon apm versions [apmRepo]
```

* `apmRepo`: Name of the APM repository. Defaults to the current project's repo (defined in `arapp.json`).

## aragon apm grant <a href="#aragon-apm-grant" id="aragon-apm-grant"></a>

Grant an address or a group of addresses the permission to create new versions in your package (defined in `arapp.json`), by interacting directly with the ACL, without performing transaction pathing.

```
aragon apm grant [addr1 ... addrN]
```

* `addresses`: The addresses being granted the permission to publish to the repo.

