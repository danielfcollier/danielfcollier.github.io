---
title: "Postgres Cheat Sheet"
date: 2022-10-22T08:42:35-03:00
Description: ""
Summary: "Useful CLI commands for the Postgres Client"
Tags: [postgres, cli, pern]
Categories: [database]
DisableComments: false
---

# Commands

## Query a Database

```bash
psql -U postgres -h <hostname> -p <port> -c '<query>' <database>
```

## Get the Table Structure

```bash
psql -U postgres -h <hostname> -p <port> -c '\d <table>' <database>
```

## Get the Database Schema

```bash
psql -U postgres -h <hostname> -p <port> -c '\dn' <database>
```

# Troubleshooting

## Verify if a Database is running

```bash
ps -ef | grep postgres
```

## Verify if Postgres Service is running

```bash
sudo fun /tmp -name .s.PGSQL.5432
psql -h /tmp <database>
```

