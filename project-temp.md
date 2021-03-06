# Step 1
## General
* project name = edge
## Schedule
* 15th ~ 27th Apr

## Target
* Server-client
* Pre-message matching worker
  * active user collector
  * message(fresh, old) collector for cycling
  * user-message matching
* Search engine for [#] autocomplete
* Mailer worker
* Backend admin
  * watching message flow
  * approve [#] requests
  * manage users

## Details
* 4.15 :: setup environment, check schedule
* :: setup matching worker (3~4 days) 
* :: setup search engine (2 days)
* :: setup mailer (1 day)
* :: setup backend admin (2~3 days)
* 4.24 :: alpha test

## Env
* Ubuntu 14.04 LTS
* Node.js(v0.12.0) - koa application for
  * server-client
  * worker(instance)
    * matching worker
    * mailer
  * backend admin
* elasticsearch server (inside instance)
* MySQL 5.6
* Redis for
  * matching worker
  * server-client session (separated database)

## Project/Instances
* [project]
* [project]Worker (+mailer)
* [project]Admin

# Step 2
## Schedule
## Target
* API
