# Packages service

Although the packages service is something package developers do not change or develop normally it is good to understand how it works as you will provide the input to it and interact with it.

## Storage

Packages are stored in a very simple way. As with most package systems \(linux, node.js, .net, maven\) we have selected plain files as carriers. The reason being that they require none or very little infrastructure, they are platform independent, easy to move, easy to understand, easy to change/deploy. And we don't need any transactional handling so involving a database or similar system does not give any value.

Currently we use AWS S3 for storage of the global packages. With that we get the benefits from versioning of files which is a nice addition but there is also a package register-file which points out what available packages there is and that can potentially point out any package file that can be reached over http\(s\).

## Package registry

The main registry file is called marketplace.yml. It only contains a list of url:s to all the available packages. The url should point to a **publically available** file. The package service \(and provisioning tool in the end\) looks at the registry and then fetches all the defined packages by fetching the URL. We will come to how a package file should look like.

![](/assets/package-reg-index.png)

### Development and pre-production

For developers and test we have added an extra registry which is included in provisioning / package service if you have the right role \(**Cloud Dev**\) connected. This is very useful if you want to start developing your own packages without risking them turning up in production. Contact support to be added as a developer.

### Deployment of a new package

To deploy a new package there are a few steps.

1. Upload \(or ask admin to upload\) your package definition file and make it public \(read\). More on format later.
2. Update \(or ask admin to update\) the registry file to include your new Package \(URL\).

For developers wanting to handle the entire process themselves in development repository we recommend the S3-filemanager "Cyberduck" as that supports transfer on save.



