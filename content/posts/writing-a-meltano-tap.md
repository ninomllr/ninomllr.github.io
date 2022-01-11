---
date: "2022-01-05T22:25:52+01:00"
draft: true
title: Writing a Meltano Tap
---

If you have read my older posts already, you will know that we at [Substring - The Data Company](https://substring.ch) decided to become more data-driven and wanted to set up a simple data warehouse for our every day business. If you want to know how our [open source data warehouse](posts/creating-an-opensource-datawarehouse-for-a-small-company) looks like check out my other post about it.

One of our most important systems in our daily business is [bexio](https://bexio.com) that we use for accounting, invoicing and tracking of billable work hours. Basically everything related to money 💵 🤑.

Now when we decided to go for [Meltano](https://meltano.com) as the data ingestion tool, we knew that there is no [Singer.io](https://singer.io) tap out there for our use case. Luckily, the team at Meltano did a great job at setting up an easy way to create new taps.

Now the end result of this blog post is a usable Singer tap for bexio. Check out the [Github project](https://github.com/substringgmbh/tap-bexio).

# Basic setup

Now I think the [official documentation](https://sdk.meltano.com/en/latest/dev_guide.html#tap-development-overview) around creating a Meltano tap is quite well done. Nonetheless I decided to create a personal blog post on what I struggled with during the development of my first Singer tap.

First, install [cookiecutter](https://cookiecutter.readthedocs.io/), a tool that creates projects from templates.

```
pip3 install pipx
pipx ensurepath
pipx install cookiecutter
pipx install poetry
```

Now initalize your project in your projects directory. Cookiecutter will ask you many questions, like the name of your tap and so on, so don't create a folder for your project first as the template will handle this for you.

```
cookiecutter https://gitlab.com/meltano/sdk --directory="cookiecutter/tap-template"
```

The whole project is initialized now, but the most important files for you are the following ones, that we go through step by step now, so that you understand what you need to change.

## client.py

First set the right url base for your api.

```
url_base = "https://api.bexio.com/2.0/"
```
