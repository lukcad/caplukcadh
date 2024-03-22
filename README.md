# caplukcadh

## Overview

This is template of basic container for development using SAP CAP approach. This can be donwloaded from git Hub into your workspace and enriched by your CDS projects whihc follows to recomendations from [SAP CAP](https://cap.cloud.sap/docs/about/).

Initial container includes:

* container with node.js;
* install of components: curl, git, sqlite3;
* non-root user: node
* workdir: home/node
* extensions for VS:
  * SAPSE.vscode-cds
  * dbaeumer.vscode-eslint
  * humao.rest-client
  * qwtel.sqlite-viewer
  * mechatroner.rainbow-csv
* installing globally during initializaiton container these libraries:
  * cds
  * hana-cli
  * cf8-cli

You should clone this by command to provide your own name of docker container project:

    git clone https://github.com/lukcad/caplukcadh.git <your_name_container_project>


You should open it by `VS code` as `contianer` and add into it as many as you wish CDS projects.

Using container:

* create CAP project

  Use this command to add new project in container:

      cds init <your_name_project>

  Use this command to add mock data into your new created project:

      cds add tiny-sample

  or

      cds add data

* create connectivity to SAP HANA cloud:

  * activate access to your Cloud Foundry in SAP BTP by preinstalled in container cf-cli using command:

        cf login

  * find name of your hana cloud from list of CF services:

        cf services

  * use preinstalled in container hana-client to accesss to your database:

        hana-cli hc

Enjoy, you have container which you can use for development your Full-Stack CAP applicaitons with access to SAP Hana Cloud based on SAP BTP CF.

Thank you,
LUKCAD.