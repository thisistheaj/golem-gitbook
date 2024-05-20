# Package Management

## Install Packages

To install a package from the registry, you can use the `install` command like so:
```
golem install @<publisher-name>/<package-name>
```
The publisher name is the NEAR account name of the person or organization that published the package.

## Uninstall Packages

To uninstall a package, you can use the `uninstall` command like so:
```
golem uninstall @<publisher-name>/<package-name>
```

## Publish Packages

Publishing uses the NEAR blockchain and IPFS, you will need an account on NEAR's testnet with some NEAR in it for gas. There are no requirements on the IPFS side.

Once you have a NEAR account, you must also install the CLI and login with it. Full and up-to-date instructions can be found [here](https://docs.near.org/docs/tools/near-cli). But the basic steps are:
```
npm install -g near-cli
near login
```
Once logged in, you can publish a package by running:
```
golem publish <package-name> <semantic-version>
```
The package name must match a folder or path in your project, and the semantic version must be a valid semantic version. By default, golem will look for the specified folder or file in the `/lib` folder, but if you specify `/app`, `/sur`, or `/mar`, in the prefix of your path, it will look in the root of that folder instead. Any valid hoon file or folder of hoon files is a valid package.

## Search Packages

You can search the registry for a package to verify that it exists by running:
```
golem search @<publisher-name>/<package-name>
```
The search command in the CLI can't perform fuzzy matching by default. Since the registry contract is decentralized, it is included to allow for easy verification of a package's existence without installing it.
