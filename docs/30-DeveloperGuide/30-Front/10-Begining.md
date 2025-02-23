---
layout: default
title: Begining
parent: Front
grand_parent: Developer guide
nav_order: 10
---

# Begining
This document explains how to customize a project based on the BIA Angular framework.   

## Change version
Update the version of the application. To do this, change the `version` variable in **src\environments\environment.ts** and **src\environments\environment.prod.ts**.   
Warning in **src\environments\environment.ts** the apiUrl could be : 'http://localhost/[ProjectName]/**WebApi**/api' or 'http://localhost/[ProjectName]/api' it depend how you have configure the backend api in IIS (or properties of the Visual studio project)
And serverLoggingUrl: 'http://localhost/JobMonitor/**WebApi**/api/logs' or http://localhost/JobMonitor/api/logs'

## File not to be modified
Some files are part of the Framework and should not be modified.

* src/app/core/bia-core
* src/app/shared/bia-shared
* src/assets/bia
* src/scss/bia
* src/app/features/sites
* src/app/features/users


## NPM Package
The content of the framework is normally sufficient for the needs of any project. You should never install any other npm package other than those provided by the Framework.   You should not use the `ng update` command.   
The component library chosen for this framework is [PrimeNG](https://www.primefaces.org/primeng/v9.1.4-lts/). You must use only these components.   
If the content of this framework is not enough, please contact first The BIATeam before installing an npm package on your project.

## Design / Layout
If you need to modify the PrimeNG component design, you can modify the following file: src\scss\\_app-custom-theme.scss   
For example you can change the row/cell size of the tables by changing the following `padding` property:
``` scss
p-table {
  td {
    font-weight: 300;
    padding: 0.414em 0.857em !important;
  }
}
```
For the layout, [angular/flex-layout](https://github.com/angular/flex-layout/wiki) is used. [Here](https://tburleson-layouts-demos.firebaseapp.com/#/docs) is a help site.
## NGRX Store
The framework and management of the store is based on this application. You can follow this example for the implementation of your store:   
[angular-contacts-app-example](https://github.com/avatsaev/angular-contacts-app-example)

## Before commit
before committing your changes, run the following commands:

* ng lint: You must have the following message: "All files pass linting".
* ng build --aot: You must not get an error message.

