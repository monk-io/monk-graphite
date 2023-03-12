# Graphite & Monk

This repository contains Monk.io template to deploy Graphite either locally or on cloud of your choice (AWS, GCP, Azure, Digital Ocean).

## Prerequisites

- [Install Monk](https://docs.monk.io/docs/get-monk)
- [Register and Login Monk](https://docs.monk.io/docs/acc-and-auth)
- [Add Cloud Provider](https://docs.monk.io/docs/cloud-provider)
- [Add Instance](https://docs.monk.io/docs/multi-cloud)

## Make sure monkd is running

```bash
foo@bar:~$ monk status
daemon: ready
auth: logged in
not connected to cluster
```

## Clone Repository

```bash
git clone https://github.com/monk-io/monk-graphite
```

## Load Template

```bash
cd monk-graphite
monk load MANIFEST
```

## Let's take a look at the themes I have installed

```bash
foo@bar:~$ monk list graphite
✔ Got the list
Type      Template     Repository  Version  Tags
runnable  graphite/db  local       -        -
```

## Deploy Stack

```bash
foo@bar:~$ monk run graphite/db
```

## Variables

| Variable        | Description                                  | Default                       |
|-----------------|----------------------------------------------|-------------------------------|
| plaintext_port  | Graphite plain text port                     | 2003                          |
| management_port | Graphite management text port                | 8126                          |
| gui_port        | Graphite management interface port text port | 80                            |
| image           | Docker image tag                             | 1.1.10-4                      |
| volume_local    | Volume path                                  | ${monk-volume-path}/timescale |

## Stop, remove and clean up workloads and templates

```bash
monk purge -a
```
