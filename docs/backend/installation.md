---
sidebar_position: 2
---

# Installation

This project depends on `Python >=3.8`, `Redis` and `PostgreSQL` to work properly, you will also need `GIT` installed on your computer to go ahead with this guide, be sure to have it installd on your computer before continuing.

## Cloning the repository

First thing we need to do before starting to configurate our project is to clone the repository, for that we will open a terminal and run the following commands.

```
$ git clone https://github.com/PuppySignal/Backend
$ cd Backend
```

## Installing the dependencies

Dependencies on this project are tracked using a tool called `poetry`, so before installing the dependencies, we will install poetry on our environment.

```
$ pip install poetry
```

Once poetry was successfuly installed, we will procced to install all the dependencies by running the next

```
$ poetry install
```

## Configurating the .env

We will need to create a `.env` file at the root directory of our project that contains the nexts keys

```
JWT_SECRET=
TWILIO_ACCOUNT_SID=
TWILIO_AUTH_TOKEN=
TWILIO_SERVICE_ID=

b2_endpoint_url=https://...
b2_application_key_id=
b2_application_key=
b2_bucket=

redis_host=
redis_port=

db_engine=postgresql
db_username=
db_password=
db_host=
db_name=puppysignal
```

`JWT_SECRET` can be any passphrase for our JWT Tokens, while the others services such as Twilio and B2 (S3) must be filled with your credentials, in the case of redis you must put the host of where your redis is running and the port of it.

## Running the migrations

To run the migrations of our models to our database is only needed to run a simple command.

```
$ alembic upgrade head
```

## Running the project

Once all the previous steps were done successfuly, you should be able to run the project easly by just running the main.py

```
$ python main.py

INFO:     Will watch for changes in these directories: ['/backend']
INFO:     Uvicorn running on http://localhost:8000 (Press CTRL+C to quit)
INFO:     Started reloader process [91150] using statreload
INFO:     Started server process [91194]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```