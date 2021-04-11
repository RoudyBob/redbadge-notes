# API Endpoint \(plancontroller\)

{% api-method method="post" host="localhost:3000/plan" path="/" %}
{% api-method-summary %}
Create Plan Entry
{% endapi-method-summary %}

{% api-method-description %}
Using parameters provided as part of the request, this will create a new plan entry in the plan\_entries table.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="date" type="string" required=true %}
 Plan Entry date
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
Plan Entry type
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=true %}
Plan Entry description
{% endapi-method-parameter %}

{% api-method-parameter name="distance" type="number" required=false %}
Plan Entry distance
{% endapi-method-parameter %}

{% api-method-parameter name="units" type="string" required=false %}
Plan Entry units
{% endapi-method-parameter %}

{% api-method-parameter name="time" type="string" required=false %}
Plan Entry duration
{% endapi-method-parameter %}

{% api-method-parameter name="notes" type="string" required=false %}
Plan Entry notes
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
"plan_entry": 
        {
        "date": "01/01/2000",
        "type": "Run",
        "description": "6 Miles Easy",
        "distance": "6",
        "units": "mi",
        "time": "",
        "notes": "Just an easy 6mi run."
        }
}
```

{% api-method method="put" host="localhost:3000/plan" path="/:id" %}
{% api-method-summary %}
Update Plan Entry
{% endapi-method-summary %}

{% api-method-description %}
Using parameters provided as part of the request, this will update a plan entry in the plan\_entries table.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of Plan Entry to Update
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="date" type="string" required=true %}
 Plan Entry date
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
Plan Entry type
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=true %}
Plan Entry description
{% endapi-method-parameter %}

{% api-method-parameter name="distance" type="number" required=false %}
Plan Entry distance
{% endapi-method-parameter %}

{% api-method-parameter name="units" type="string" required=false %}
Plan Entry units
{% endapi-method-parameter %}

{% api-method-parameter name="time" type="string" required=false %}
Plan Entry duration
{% endapi-method-parameter %}

{% api-method-parameter name="notes" type="string" required=false %}
Plan Entry notes
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
"plan_entry": 
        {
        "date": "01/01/2000",
        "type": "Run",
        "description": "6 Miles Easy",
        "distance": "6",
        "units": "mi",
        "time": "",
        "notes": "Just an easy 6mi run."
        }
}
```

{% api-method method="get" host="localhost:3000/plan" path="/mine" %}
{% api-method-summary %}
Get All Plan Entries for Current User
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

{% api-method method="get" host="localhost:3000/plan" path="/:ownerid" %}
{% api-method-summary %}
Get All Plan Entires for OwnerID
{% endapi-method-summary %}

{% api-method-description %}
This will get all plan entries for a specific owner. This would be used by a coach to see all the plan entries for one of the runners they coach.
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

{% api-method method="delete" host="localhost:3000/plan" path="/:id" %}
{% api-method-summary %}
Delete Plan Entry by ID
{% endapi-method-summary %}

{% api-method-description %}
This will delete the plan entry for the specified ID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of entry to delete
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

