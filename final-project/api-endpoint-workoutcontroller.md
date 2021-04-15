# API Endpoint \(workoutcontroller\)

{% api-method method="post" host="localhost:3000/workout" path="/" %}
{% api-method-summary %}
Create Workout Entry
{% endapi-method-summary %}

{% api-method-description %}
Using parameters provided as part of the request, this will create a new workout entry in the workout\_entries table.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="timestamp" type="string" required=true %}
Workout entry timestamp
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=true %}
Workout entry description
{% endapi-method-parameter %}

{% api-method-parameter name="distance" type="number" required=false %}
Workout entry distance
{% endapi-method-parameter %}

{% api-method-parameter name="units" type="string" required=false %}
Workout entry units
{% endapi-method-parameter %}

{% api-method-parameter name="movingtime" type="number" required=false %}
Workout entry moving time
{% endapi-method-parameter %}

{% api-method-parameter name="elapsedtime" type="number" required=false %}
Workout entry elapsed time
{% endapi-method-parameter %}

{% api-method-parameter name="elevationgain" type="number" required=false %}
Workout entry elevation gain
{% endapi-method-parameter %}

{% api-method-parameter name="startlocation" type="array" required=false %}
Workout entry GPS starting location
{% endapi-method-parameter %}

{% api-method-parameter name="endlocation" type="array" required=false %}
Workout entry GPS ending location
{% endapi-method-parameter %}

{% api-method-parameter name="temp" type="number" required=false %}
Workout entry temperature
{% endapi-method-parameter %}

{% api-method-parameter name="humidity" type="number" required=false %}
Workout entry humidity
{% endapi-method-parameter %}

{% api-method-parameter name="aqi" type="number" required=false %}
Workout entry Air Quality Index
{% endapi-method-parameter %}

{% api-method-parameter name="notes" type="string" required=false %}
Workout entry notes
{% endapi-method-parameter %}

{% api-method-parameter name="sourceid" type="string" required=false %}
Source ID if importing from another service
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Example Body Request

```javascript
{
"workout_entry": 
        {
        "timestamp": "01/01/2020:00:00:00Z",
        "description": "Another Workout",
        "distance": "6",
        "units": "standard",
        "movingtime": "",
        "elapsedtime": "",
        "elevationgain": "439",
        "startlocation": "[]",
        "endlocation": "[]",
        "temp": "63",
        "humidity": "72",
        "aqi": "23",
        "notes": "What a great run."
        "sourceid": ""
        }
}
```

{% api-method method="put" host="localhost:3000/workout" path="/" %}
{% api-method-summary %}
Update Workout Entry
{% endapi-method-summary %}

{% api-method-description %}
Using parameters provided as part of the request, this will update a workout entry in the workout\_entries table.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="timestamp" type="string" required=true %}
Workout entry timestamp
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=true %}
Workout entry description
{% endapi-method-parameter %}

{% api-method-parameter name="distance" type="number" required=false %}
Workout entry distance
{% endapi-method-parameter %}

{% api-method-parameter name="units" type="string" required=false %}
Workout entry units
{% endapi-method-parameter %}

{% api-method-parameter name="movingtime" type="number" required=false %}
Workout entry moving time
{% endapi-method-parameter %}

{% api-method-parameter name="elapsedtime" type="number" required=false %}
Workout entry elapsed time
{% endapi-method-parameter %}

{% api-method-parameter name="elevationgain" type="number" required=false %}
Workout entry elevation gain
{% endapi-method-parameter %}

{% api-method-parameter name="startlocation" type="array" required=false %}
Workout entry GPS starting location
{% endapi-method-parameter %}

{% api-method-parameter name="endlocation" type="array" required=false %}
Workout entry GPS ending location
{% endapi-method-parameter %}

{% api-method-parameter name="temp" type="number" required=false %}
Workout entry temperature
{% endapi-method-parameter %}

{% api-method-parameter name="humidity" type="number" required=false %}
Workout entry humidity
{% endapi-method-parameter %}

{% api-method-parameter name="aqi" type="number" required=false %}
Workout entry Air Quality Index
{% endapi-method-parameter %}

{% api-method-parameter name="notes" type="string" required=false %}
Workout entry notes
{% endapi-method-parameter %}

{% api-method-parameter name="sourceid" type="string" required=false %}
Source ID if importing from another service
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Example Body Request

```javascript
{
"workout_entry": 
        {
        "timestamp": "01/01/2020:00:00:00Z",
        "description": "Another Workout",
        "distance": "6",
        "units": "standard",
        "movingtime": "",
        "elapsedtime": "",
        "elevationgain": "439",
        "startlocation": "[]",
        "endlocation": "[]",
        "temp": "63",
        "humidity": "72",
        "aqi": "23",
        "notes": "What a great run."
        "sourceid": ""
        }
}
```

{% api-method method="get" host="localhost:3000/workout" path="/mine" %}
{% api-method-summary %}
Get All Workout Entries for Current User
{% endapi-method-summary %}

{% api-method-description %}
This will get all plan entries for the current user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="localhost:3000/workout" path="/:ownerid" %}
{% api-method-summary %}
Get All Workout Entires for OwnerID
{% endapi-method-summary %}

{% api-method-description %}
This will get all workout entries for a specific owner. This would be used by a coach to see all the workout entries for one of the runners they coach.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="ownerid" type="string" required=true %}
ID of Owner to Get Plan Entries For
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="localhost:3000/workout" path="/:id" %}
{% api-method-summary %}
Delete Workout Entry by ID
{% endapi-method-summary %}

{% api-method-description %}
This deletes the workout entry for the specified ID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
workout entry ID to delete
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

