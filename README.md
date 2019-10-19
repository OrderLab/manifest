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

