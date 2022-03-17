
# Usecases Info (EBRAINS CLS-Interactive)

This repository contains all the information related to the use cases that are shown in the

**EBRAINS Cellular Level Simulation Interactive Workflows and Use Cases** [portal](https://www.ebrains.eu/service/cls-interactive).

All the titles, images, descriptions, files, etc are reported in [usecases-info.json](usecases-info.json) configuration file.
This app is deployed in the portal's "Workflows and Use Cases" [page](https://ebrains-cls-interactive.github.io/online-use-cases.html).

## For developers
The information concerning the use cases, which is reported in the [usecases-info.json](usecases-info.json) file, is instrumental to build the [Wizard](https://github.com/BlueBrain/bsp-usecase-wizard).

When pushed to the `develop` branch, you can see the results at https://bluebrain.github.io/bsp-usecase-wizard/dev/index.html.

When pushed to the `main` branch, you can see the results at https://bluebrain.github.io/bsp-usecase-wizard/index.html.

### How to Add new Use Cases
You can find a short tutorial on how to use new Use Cases [here](/documentation/add_new_usecase.md).

### To format json
In order to format the json file, please use the following node.js command:

`npx js-beautify -f usecases-info.json -r -k -s 2 -b preserve-inline -n`
