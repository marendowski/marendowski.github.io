+++
title = "How to set up PostgreSQL on Arch Linux"
date = "2025-03-21"
tags = ["technical", "howto"]
+++

About setting up [PostgreSQL](https://www.postgresql.org/) on [Arch Linux](https://archlinux.org/).

<!--more-->

![PostgreSQL logo](postgres_logo.png)

# TL;DR

1. Install the `postgresql` package.

```
sudo pacman -S postgresql
```

2. Intialize a data database as the `postgres` user.

```
sudo -i -u postgres
[postgres@archlinux ~]$ psql
postgres=> initdb --locale=C.UTF-8 --encoding=UTF8 -D '/var/lib/postgres/data'
```

4. Enable and start the `postgresql` service.

```
sudo systemctl enable postgresql
sudo systemctl start postgresql
```

5. Enter `psql` and create a new database with your user.

```
sudo -u postgres psql
postgres=# create database MYUSER;
postgres=# create user MYUSER with password 'MYPASSWORD';
postgres=# grant all privileges on database MYUSER to MYUSER;
```

[More reading](https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e)
