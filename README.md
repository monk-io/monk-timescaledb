# Time Scale DB & Monk

This repository contains Monk.io template to deploy TimescaleDB either locally or on cloud of your choice (AWS, GCP, Azure, Digital Ocean).

## Prerequisites

- [Install Monk](https://docs.monk.io/docs/get-monk)
- [Register and Login Monk](https://docs.monk.io/docs/acc-and-auth)
- [Add Cloud Provider](https://docs.monk.io/docs/cloud-provider)
- [Add Instance](https://docs.monk.io/docs/multi-cloud)

### Make sure monkd is running

```bash
foo@bar:~$ monk status
daemon: ready
auth: logged in
not connected to cluster
```

## Clone Repository

```bash
git clone https://github.com/monk-io/timescaledb
```

## Load Template

```bash
cd timescaledb
monk load MANIFEST
```

### Let's take a look at the themes I have installed

```bash
foo@bar:~$ monk list timescaledb
✔ Got the list
Type      Template          Repository  Version  Tags
runnable  timescaledb/base  local       -        -
runnable  timescaledb/db    monk        -        -
```

## Deploy Stack

```bash
foo@bar:~$ monk run timescaledb/db
```

## Variables

The variables are in `timescaledb.yml` file. You can quickly setup by editing the values here.

| Variable    | Description      | Default     |
| ----------- | ---------------- | ----------- |
| image       | Docker image tag | pg14-latest |
| db_password | DB Password      | monk        |

## Stop, remove and clean up workloads and templates

```bash
monk purge -a
```
