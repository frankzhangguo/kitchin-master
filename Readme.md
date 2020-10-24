# Delivery system simulation
Real-time system that emulates the fulfillment of delivery orders for a kitchen.

# Getting started
This system is built by using Java language. 

Unzip the Source code
## Maven Build
Local environment is used by default, The configuration file：`application.properties`


## Generated code structure

## Startup Project
Project Main Class: `SimpleApplication.java`

# System design

## Decision Rationale:

* I used redis as the core communication layer for the app. I havent used redis specifically before, most of my queue experience is with AWS SQS and celery. It seemed like the best tool for the job though, and I believe its also part of your stack. This project ended up being a pretty fun way to get some experience with redis.
* For the overflow shelf I used an npm library to lock down the section of code that would add to, or replace a random item with a new item. This was to ensure that there would not be race conditions and end up with 16 or 17 items on the shelf. The locking library I used doesnt mesh perfectly with the redis client I used in the rest of the application, given more time I would probably build a better locking utility, or _maybe_ consider migrating over to the redis client it preferred, but since that client doesnt support async/await, thats doubtful.
* Full disclosure, I ran out of time to implement moving overflow orders back to their respective temperature shelf, I only had sunday afternoon to work on this with my current job.


# Contact
> frankzhangguo@qq.com


