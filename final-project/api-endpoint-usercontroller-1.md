# API Endpoint \(usercontroller\)

{% api-method method="post" host="localhost:3000/user" path="/signup" %}
{% api-method-summary %}
Create User
{% endapi-method-summary %}

{% api-method-description %}
Using parameters provided as part of the request, this will create a new user in the users table.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="firstname" type="string" required=false %}
First name of the user
{% endapi-method-parameter %}

{% api-method-parameter name="lastname" type="string" required=true %}
Last name of the user
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email of the user \(also username\)
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Password of the user
{% endapi-method-parameter %}

{% api-method-parameter name="birthdate" type="string" required=true %}
\(type: date\) Birthdate of the user
{% endapi-method-parameter %}

{% api-method-parameter name="weekstart" type="string" required=true %}
First day of the week \(default: monday\)
{% endapi-method-parameter %}

{% api-method-parameter name="defaultunits" type="string" required=true %}
Units preferences - standard/metric \(standard\)
{% endapi-method-parameter %}

{% api-method-parameter name="coach" type="boolean" required=true %}
Is the user a coach?
{% endapi-method-parameter %}

{% api-method-parameter name="coachedrunners" type="array" required=false %}
Array of ownerIDs that are coached
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
"user": 
        {
        "firstname": "Test",
        "lastname": "User",
        "email": "test@test.com",
        "password": "12345",
        "birthdate": "01/01/2000",
        "weekstart": "monday",
        "defaultunits": "mi",
        "coach": "true"
        "coachedrunners": "[]"
        }
}
```

{% api-method method="put" host="localhost:3000/user" path="/:id" %}
{% api-method-summary %}
Update User
{% endapi-method-summary %}

{% api-method-description %}
Using parameters provided as part of the request, this will update the user linked to the ID specified as part of the path. Will require to be the logged in user or if they are updating coachedrunners, any authenticated users can update that column.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=false %}
authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="id" type="string" required=false %}
Owner ID to Update
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="firstname" type="string" required=false %}
First name of the user
{% endapi-method-parameter %}

{% api-method-parameter name="lastname" type="string" required=true %}
Last name of the user
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email of the user \(also username\)
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Password of the user
{% endapi-method-parameter %}

{% api-method-parameter name="birthdate" type="string" required=true %}
\(type: date\) Birthdate of the user
{% endapi-method-parameter %}

{% api-method-parameter name="weekstart" type="string" required=true %}
First day of the week \(default: monday\)
{% endapi-method-parameter %}

{% api-method-parameter name="defaultunits" type="string" required=true %}
Units preferences - standard/metric \(standard\)
{% endapi-method-parameter %}

{% api-method-parameter name="coach" type="boolean" required=true %}
Is the user a coach?
{% endapi-method-parameter %}

{% api-method-parameter name="coachedrunners" type="array" required=false %}
Array of ownerIDs that are coached
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
"user": 
        {
        "firstname": "Test",
        "lastname": "User",
        "email": "test@test.com",
        "password": "12345",
        "birthdate": "01/01/2000",
        "weekstart": "monday",
        "defaultunits": "mi",
        "coach": "true"
        "coachedrunners": "[]"
        }
}
```

{% api-method method="post" host="localhost:3000/user" path="/login" %}
{% api-method-summary %}
Login
{% endapi-method-summary %}

{% api-method-description %}
Will attempt to authenticate using the email and password provided.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="password" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

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
"user": 
        {
        "email": "test@test.com"
        "password": "12345"
        }
}
```

{% api-method method="get" host="localhost:3000/user" path="/" %}
{% api-method-summary %}
Get All Users
{% endapi-method-summary %}

{% api-method-description %}
Will get a list of all users. Not authenticated.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

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

