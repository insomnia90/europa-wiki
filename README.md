# API docs
**API mounting route** `<host_url>/api`

## HTTP Header

**Authorization Header:**

`X-Access-Token` : `<access_token>`


## User and Authentication

#### Create profile_admin User
> Note: This is boss.

**Method** `POST` **URL** `/admin/users`

**Request:**
`{
  "email": <email>,
  "password": <password>,
  "is_profile_admin": true
}`

**Response:**

> StatusCode:
`200 or 500`

> Body: `null`


#### Create employee User

**Method** `POST` **URL** `/users`

**Request:**
`{
  "email": <email>,
  "password": <password>,
  "is_profile_admin": false // true if user is owner
}`

**Response:**

> StatusCode:
`200 or 500`

> Body: `null`


#### Get auth token

**Method** `POST` **URL** `/auth/token`

**Request:**
`{
  "email": <email>,
  "password": <password>
}`

**Response:**

> StatusCode:
`500` Server error

>> Body: `null`

> StatusCode:
`200`
>> Body:
`{
  "success": <true|false>,
  "exp": "72h",
  "token": <token>,
}`


## Resources

Profile **Method** `POST` `GET` **URL** `/profiles`

Product **Method** `POST` `GET` **URL** `/products`

Delegate **Method** `POST` `GET` **URL** `/delegates`

Bill **Method** `POST` `GET` **URL** `/bills`

## Pagination
Url query `/bills?page=x&per_page=y` 
