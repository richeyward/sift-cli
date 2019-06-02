![Logo](https://digital-forensics.sans.org/images/sift.png)

# SIFT CLI
This is a **WORK IN PROGRESS** project to try to migrate the SIFT workstation to Ubuntu 18.04.  Consider this broken,

A minimal Ubuntu installation was installed and the following actions were performed.

## General Setup
The following is required to get a base install working.

### Base desktop install
The decision to install MATE was taken as it's fairly lightweight.

`sudo apt install ubuntu-mate-core xinit lightdm`

### Sift CLI install
These are tools used for building the sift-cli package. This is only required if you are intending to compile the package yourself.

`sudo apt install nodejs npm jo git`

### GPG Key create
A locally generated GPG key is needed to sign the package. Not mandatory but good to do.

`gpg --generate-key`

Insert last 8 chars from the key into the package.json, line 13

### Install npm packages
```
cd sift-cli

npm install```

### Generate the sift-cli binary
This will be stored alongside the GPG key in the releases directory

`npm run pkg`

### Execute sift-cli
Run the newly created executable with:

`sudo ./release/sift-cli-linux`
