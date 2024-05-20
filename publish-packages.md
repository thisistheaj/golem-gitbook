# Publish Packages

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
