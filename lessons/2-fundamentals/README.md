# 2. Fundamentos de GitHub Actions

## Índice

[1. Workflows](#1-workflows)
[2. Jobs](#2-jobs)

## 1. Workflows

Un flujo de trabajo tiene un nombre asignado y se dispara cuando se produce un evento determinado, por ejemplo al hacer push en la rama main:

    name: Basic workflow example

    on:
      push:
        branches:
          - main

A partir de ahí, hay que definir los trabajos que realizará dicho flujo, con sus pasos correspondientes:

    jobs:
      deploy:
        runs-on: ubuntu-18.04
        steps:

Que a su vez pueden ser comandos ejecutables por consola en el runner asignado, o acciones de GitHub:

    steps:
      - name: Downloading project
        uses: actions/checkout@v3
        with:
          fetch-depth: 0
      - name: Installing Node
        uses: actions/setup-node@v3
        with:
          node-version: 18
      - name: Installing dependencies
        run: npm ci

## 2. Jobs

.

## Referencias

[Tutorial de introducción](https://www.adictosaltrabajo.com/2020/10/28/introduccion-a-github-actions-sintaxis-basica/)

[Workflows](https://docs.github.com/en/actions/using-workflows/about-workflows)  
[Jobs](https://docs.github.com/en/actions/using-jobs/using-jobs-in-a-workflow)

[Marketplace GitHub Actions](https://github.com/marketplace?type=actions)
