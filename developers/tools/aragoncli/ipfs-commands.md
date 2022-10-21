# IPFS commands

{% hint style="info" %}
The `aragon ipfs` commands can be used to <mark style="color:blue;">start an IPFS node</mark> configured to pin the core Aragon components, inspect hashes, and propagate files to other nodes.
{% endhint %}

## aragon ipfs <a href="#aragon-ipfs" id="aragon-ipfs"></a>

Shortcut for `aragon ipfs start`.

```
aragon ipfs
```

## aragon ipfs start <a href="#aragon-ipfs-start" id="aragon-ipfs-start"></a>

Start the IPFS daemon and configure it to work with Aragon.

```
aragon ipfs start
```

## aragon ipfs status <a href="#aragon-ipfs-status" id="aragon-ipfs-status"></a>

Status of the IPFS installation & daemon.

```
aragon ipfs status
```

Options:

* `--repo-path`: The location of the IPFS repository

## aragon ipfs install <a href="#aragon-ipfs-install" id="aragon-ipfs-install"></a>

Download and install the go-ipfs binaries.

```
aragon ipfs install
```

Options:

* `--dist-version`: The version of IPFS that will be installed. Defaults to `0.4.22`.
* `--dist-url`: The url from which to download IPFS. Defaults to `https://dist.ipfs.io`.
* `--local`: Whether to install IPFS as a project dependency. Defaults `false`.
* `--skip-confirmation`: Whether to skip the confirmation step. Defaults to `false`.

## aragon ipfs uninstall <a href="#aragon-ipfs-uninstall" id="aragon-ipfs-uninstall"></a>

Uninstall the go-ipfs binaries.

```
aragon ipfs uninstall
```

Options:

* `--local`: Whether to uninstall IPFS from the project dependencies. Defaults `false`.
* `--skip-confirmation`: Whether to skip the confirmation step. Defaults to `false`.

## aragon ipfs propagate <a href="#aragon-ipfs-propagate" id="aragon-ipfs-propagate"></a>

Request the content and its links at several gateways, making the files more distributed within the network.

```
aragon ipfs propagate <cid>
```

Positionals:

* `cid`: A self-describing content-addressed identifier

## aragon ipfs view <a href="#aragon-ipfs-view" id="aragon-ipfs-view"></a>

Display metadata about the content, such as size, links, etc.

```
aragon ipfs view <cid>
```

Positionals:

* `cid`: A self-describing content-addressed identifier



> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/c/dev-support/20" %}
