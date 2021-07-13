# Registration

{% api-method method="post" host="https://my.endpoint.ybrid.io" path="/ctrl/v2/admin/services/service/item/register" %}
{% api-method-summary %}
Register Item
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to register external media assets.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}
Service administration token
{% endapi-method-parameter %}

{% api-method-parameter name="service-id" type="boolean" required=true %}
Whether the cake should be gluten-free or not.    
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{    "name": "Cake's name",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="First Tab" %}

{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

