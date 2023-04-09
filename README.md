# GridDB & Monk

This repository contains Monk.io template to deploy GridDB either locally or on cloud of your choice (AWS, GCP, Azure, Digital Ocean).

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
git clone https://github.com/monk-io/griddb
```

## Load Template

```bash
cd griddb
monk load MANIFEST
```

### Let's take a look at the themes I have installed

```bash
foo@bar:~$ monk list griddb
✔ Got the list
Type      Template       Repository  Version  Tags
runnable  griddb/griddb  local       -        -
```

## Deploy Stack

```bash
foo@bar:~$ monk run griddb/griddb
```

## Variables

The variables are in `griddb.yml` file. You can quickly setup by editing the values here.

| Variable      | Description          | Default     |
|---------------|----------------------|-------------|
| image_tag     | Docker image tag     | 4.6.1-focal |
| cluster_name  | Cluster name         | monk        |
| password      | DB Password          | monk        |
| notif_port    | Notification Port    | 31999       |
| notif_member  | Notification Member  | 1           |
| notif_address | Notification Address | 239.0.0.1   |

## Stop, remove and clean up workloads and templates

```bash
monk purge -a
```
