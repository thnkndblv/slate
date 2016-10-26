---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.


# Login

```shell
curl -X POST "https://hackathon.kueski.com/service/facebook/signin"
```

> The above command returns JSON structured like this:

```json
{
  "session_id": "string"
}
```

Log in to Kueski

### HTTP Request

`POST /service/facebook/signin`

### Query Parameters

Parameter | Description
--------- | -----------
access_token | Token obtained after logging in via Facebook


# User

```shell
curl "https://hackathon.kueski.com/service/user"
  --cookie "kueski_session=the_session_id_retrieved_with_the_signin"
```

> The above command returns JSON structured like this:

```json
  {
    "limits": {
      "money": 1500,
      "interest": 0.01,
      "penality_interest": 0.012,
      "time": 30,
      "loan_level": 0
    },
    "loan_exists": false,
    "loan_disbursed": false,
    "loan_status": null,
    "loan_id": "0f0f00120f0a0b0c0",
    "user_id": "0f010200f0a01020a",
    "id": "0f0f00120f0a0b0c0",
    "is_recurrent": false
  }
```

### HTTP Request

`GET /service/user`

### Query Parameters

Parameter | Description
--------- | -----------
access_token | Token obtained after logging in via Facebook


# Apply for a loan

```shell
curl "https://hackathon.kueski.com/service/apply/start"
  --cookie "kueski_session=the_session_id_retrieved_with_the_signin"
```

> The above command returns JSON structured like this:

```json
  {
    "limits": {
      "money": 1500,
      "interest": 0.01,
      "penality_interest": 0.012,
      "time": 30,
      "loan_level": 0
    },
    "loan_exists": false,
    "loan_disbursed": false,
    "loan_status": null,
    "loan_id": "0f0f00120f0a0b0c0",
    "user_id": "0f010200f0a01020a",
    "id": "0f0f00120f0a0b0c0",
    "is_recurrent": false
  }
```

### HTTP Request

`POST /service/apply/start`

### Query Parameters

Parameter | type |Description
--------- | ---- | -----------
requested_money | String | The amount of money requested
requested_days | String | The amount of days requested
