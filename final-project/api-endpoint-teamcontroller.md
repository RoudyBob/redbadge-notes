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

