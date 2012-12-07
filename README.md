Development challenge. 
======================

You will be writing a JSON REST server in python that will allow CRUD functionallity for tracking project development time estimation. Data storage is up to you, but you must document any packages/requirements to get your server up and running.

DATA
----

The following data needs to be accessible:
```
    id - The ID of the project
    title - The name of the project being estimated
    estimate - The number of days you expect this project to take
    start - The Unix time at which you started working on this project
    finish - The Unix time at which you finished working on this project
    notes - Any notes that need to be recorded about this project
```

API
---

* `create → POST`
* `read → GET`
* `update → PUT`
* `delete → DELETE`

GET PROJECTS
------------

* `GET /projects` will return all active projects.
    
```json    
[ 
    {
        "id":547201,
        "title":"Andromeda",
        "estimate":30,
        "start":1354601564,
        "finish":,
        "notes":""
    },
    {
        "id":547202,
        "title":"Milkyway",
        "estimate":15,
        "start":1354301564,
        "finish":1354572853,
        "notes":"This was much simpler than I had anticipated"
    }
]
```
    
GET PROJECT
-----------

* `GET /projects/547202` will return the specified project.

```json    
{
    "id":547202,
    "title":"Milkyway",
    "estimate":15,
    "start":1354301564,
    "finish":1354572853,
    "notes":"This was much simpler than I had anticipated"
}
```
    
CREATE PROJECT
--------------

* `POST /projects` will create a new project from the parameters passed.

```json    
{
    "title":"Milkyway",
    "estimate":15
}
```
    
This must return 201 Created, with the location of the new project in the Location header along with the current JSON representation of the project if the creation was a success.
    
    
UPDATE PROJECT
--------------

* `PUT /projects/547202` will update the project from the parameters passed.

```json    
{
    "finish":1354572853,
    "notes":"This was much simpler than I had anticipated"
}
```
    
This must return 200 OK if the update was a success along with the current JSON representation of the project.

    
DELETE PROJECT
--------------
    
* `DELETE /projects/547202` will delete the project specified and return 204 No Content if that was successful
