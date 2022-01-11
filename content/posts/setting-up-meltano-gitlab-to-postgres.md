---
date: "2022-01-11T17:51:02+01:00"
draft: true
title: Setting Up Meltano Gitlab to Postgres
---

# Setting up the ingestion

First we setup Meltano

```
# Create and activate virtual environment, and update pip
python3 -m venv .venv
source .venv/bin/activate
pip3 install pip --upgrade

# Install Meltano
pip3 install meltano

# Initialize a new Meltano project
meltano init demo-project
```

Now you can check out your project in Visual Studio code or any other editor that you like.
