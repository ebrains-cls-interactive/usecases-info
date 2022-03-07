
# Usecases Info
This repository contains all the information related to the use cases that are shown in the Cellular Level Simulation.

All the titles, images, descriptions, files, etc are described in [usecases-info.json](usecases-info.json)

### This app is deployed in [EBrains](https://ebrains-cls-interactive.github.io/online-use-cases.html)

## For developers
This information is used to build the [Wizard](https://github.com/BlueBrain/bsp-usecase-wizard)

When pushed to `develop` branch, you can see the results at https://bluebrain.github.io/bsp-usecase-wizard/dev/index.html

When pushed to `main` branch, you can see the results at https://bluebrain.github.io/bsp-usecase-wizard/index.html

### How to Add new [use case](/documentation/add_new_usecase.md)

### To format json
`npx js-beautify -f usecases-info.json -r -k -s 2 -b preserve-inline -n`
