# europa

## API docs

### HTTP Header

**Authorization Header:**

`"Authorization"` : `"Bearer <access_token>"`



### User and Authentication

#### Create new user

**Method** `POST` **URL** `/api/auth`

**Request:**
`{
  "e": <email>,
  "p": <password>
}`

**Response:**

> StatusCode:
<span style="color:green">`200`</span> or <span style="color:red">`500`</span>

**Body:** `null`


#### Login
**Method** `POST` **URL** `/api/auth/token`

**Request:**
`{
  "e": <email>,
  "p": <password>
}`

**Response:**
> StatusCode: <span style="color:green">`200`</span>

>> Body:
`{
  "access_token" : <some long token>,
  "token_type" : "bearer",
  "exp" : <expiration date for token>
}`

> StatusCode: <span style="color:red">`500`</span>

---

### Bill Resource

#### Insert new bill
**Method** `POST` **URL** `/api/bill`

**Request:**
`{
  "Vendor": <>
  "CIF": <>
  "Adress": <>
  "State": <>
  "IBAN": <>
  "Bank": <>
  "Phone": <>
  "Fax": <>
  "Email": <>
  "Web": <>,
  "Capital": <>,
  "No": <>,
  "Series": <>
}`

**Response:**
> StatusCode:
  <span style="color:green">`200`</span>

>> Body:
  `null`

>> **TODO** Should return the mongo `id` of the inserted document

> StatusCode:
  <span style="color:red">`500`</span>

>> Body: `null`


#### Get all bills
**Method** `GET` **URL** `/api/bills`

**Response:**

Returns an `array []` of `Bill` model.

> StatusCode:
<span style="color:green">`200`</span>

>> Body: `[{}, ...]`

> StatusCode:
<span style="color:red">`500`</span>
>> Body: `null`


#### Get bill by `id`
**Method** `GET` **URL** `/api/bill/{id}`

**Response:**

Returns one document of type `Bill` with additional fields:
`ID, UserID`

> StatusCode:
<span style="color:green">`200`</span>

>> Body: `<{}>`

> StatusCode:
<span style="color:red">`500`</span>
>> Body: `null`
