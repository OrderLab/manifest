S2E Source Manifests
====================

This repository contains the ``repo`` manifests to manage S2E's repositories.
Compared to the official S2E manifest repo, we specified the commit IDs of
core S2E components in the stable versions that worked for the Violet project.

```
    sudo apt-get install repo
    repo init -u git@github.com:OrderLab/s2e-manifest.git
    repo sync
```

To use this modified manifest for the Violet project, you will need to install our 
slightly modified [s2e-env repo](https://github.com/OrderLab/s2e-env) instead 
of the official s2e-env repo.

If you have previously checked out the repo using the official S2E manifests, make
sure you delete those projects that we customized. For example, if your 
`libs2eplugins` is pointing to the official S2E repo, you should 
```
    rm -rf $S2EDIR/source/s2e/libs2eplugins
    rm -rf $S2EDIR/source/s2e/.repo/projects/libs2eplugins.git
    s2e update
```
**Make sure you have backed up outstanding changes before executing the above commands**
The list of projects that we customized can be found in [default.xml](default.xml)
where the project name begins with `OrderLab/`.
