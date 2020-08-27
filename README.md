S2E Source Manifests
====================

This repository contains the ``repo`` manifests to manage S2E's repositories.
Compared to the official S2E manifest repo, we specified the commit IDs of
core S2E components in the stable versions that worked for the Violet project.

```
    sudo apt-get install repo
    repo init -b violet-release -u https://github.com/OrderLab/violet-s2e-manifest.git
    repo sync
```

To use this modified manifest for the Violet project, you will need to install 
our modified [s2e-env repo](https://github.com/OrderLab/violet-s2e-env) instead 
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

Start Working
------------

When initially checked out, all the repositories are in a detached state. In order 
to work on our custom repositories, we need to set the branch to the remote branch. 
All the custom repositories are in a group called `violet`, so we can use the
`repo forall` command to batch apply a command.

Type the following command to test first:

```
  repo forall -g violet -c 'git status'
```

This should succeed and output the status for all custom repos.

Type the following command to checkout all custom repos to the `violet` branch
(our development branch):

```
  repo forall -g violet -c 'git checkout --track s2e-private/violet'
```
