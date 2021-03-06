# Add Task

Used to add new Task Data.

**URL** : `/Task/`

**Method** : `POST`

**Auth required** : YES

**Permission required** : NO

**Data constraints**

```json
{
    "title": "[Not Empty]",
    "description": "[Not Empty]",
}
```

**Data example**

```json
{
    "title": "new tasks",
    "description": "new tasks",
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
    "name": "new Category"
}
```

## Error Response

**Condition** : If 'name' is empty

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
    {
        [
            {
                "message": "Title Required",
                "type": "Validation error",
                "path": "title",
                "value": "lululu",
                "origin": "FUNCTION",
                "instance": {
                    "id": null,
                    "title": "lululu",
                    "description": "cekcek",
                    "updatedAt": "2020-12-04T07:18:08.324Z"
                },
                "validatorKey": "isNull",
                "validatorName": "isNull",
                "validatorArgs": [
                    {
                        "msg": "Title Required",
                        "ignore_whitespace": false
                    }
                ],
                "original": {
                    "validatorName": "isNull",
                    "validatorArgs": [
                        {
                            "msg": "Title Required",
                            "ignore_whitespace": false
                        }
                    ]
                }
            },
            {
                "message": "description Required",
                "type": "Validation error",
                "path": "description",
                "value": "cekcek",
                "origin": "FUNCTION",
                "instance": {
                    "id": null,
                    "title": "lululu",
                    "description": "cekcek",
                    "updatedAt": "2020-12-04T07:18:08.324Z"
                },
                "validatorKey": "isNull",
                "validatorName": "isNull",
                "validatorArgs": [
                    {
                        "msg": "description Required",
                        "ignore_whitespace": false
                    }
                ],
                "original": {
                    "validatorName": "isNull",
                    "validatorArgs": [
                        {
                            "msg": "description Required",
                            "ignore_whitespace": false
                        }
                    ]
                }
            }
        ]
    }
}
```

**Condition** : If there is an error request from server

**Code** : `500 Internal Server Error`

**Content** : 
```json
{
    "error": "Internal Server Error"
}
```