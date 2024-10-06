Workflow Template
-----------------

This repository contains the template for a GridLAB-D workflow project.

Concept of Operations
---------------------

Workflow projects are GridLAB-D simulations that require multiple steps to complete.  The actions are specified in the files, e.g., `.github/workflows/main.yml`.

Testing locally
---------------

Before running `act` using your local docker installation, you must add the following to `~/.actrc`:

    --container-daemon-socket -
    --artifact-server-path artifacts

You can test your new workflow project locally before deploying it on GitHub using `act`. See https://github.com/nektos/act for details.  After installing `act` you can run the command

    docker pull lfenergy/arras:latest
    act -P gridlabd=lfenergy/arras:latest -W .github/workflows/main.yml

where `main.yml` is the name your workflow YML file.

Customization
-------------

There are number of options that can be customized in your workflow.

  * Container name: You can change the name and version of the container by changing the value of `runs_on`.

