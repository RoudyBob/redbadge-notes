# API Endpoint \(teamcontroller\)

{% api-method method="post" host="localhost:3000/workout" path="/" %}
{% api-method-summary %}
Create Team Entry
{% endapi-method-summary %}

{% api-method-description %}
Using parameters provided as part of the request, this will create a new team entry in the teams table.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="firstname" type="string" required=true %}
First name of coach
{% endapi-method-parameter %}

{% api-method-parameter name="lastname" type="string" required=true %}
Last name of coach
{% endapi-method-parameter %}

{% api-method-parameter name="runnerid" type="array" required=false %}
Array containing IDs of runners
{% endapi-method-parameter %}

{% api-method-parameter name="userId" type="integer" required=false %}
ID of owner from users table
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
"team": 
        {
         "firstname": "Joe",
         "lastname": "User",
         "runners": [1, 3, 35]
        }
}
```

{% api-method method="put" host="localhost:3000/team" path="/join/:teamid" %}
{% api-method-summary %}
Join Current User to Team
{% endapi-method-summary %}

{% api-method-description %}
Adds userId of current user to list of runners on the team ID specified in the query.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="teamid" type="integer" required=true %}
Team ID to join
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

{% api-method method="put" host="localhost:3000/team" path="/leave/:teamid" %}
{% api-method-summary %}
Remove Current User from Team
{% endapi-method-summary %}

{% api-method-description %}
Removes userId of current user from list of runners on the team ID specified in the query
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="teamid" type="integer" required=true %}
Team ID to join
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

{% api-method method="delete" host="localhost:3000/team" path="/:id" %}
{% api-method-summary %}
Delete Team Entry
{% endapi-method-summary %}

{% api-method-description %}
Will delete the team entry in the teams table for the id specified only if the current user owns the team.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
authorization token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
ID of team to delete
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

