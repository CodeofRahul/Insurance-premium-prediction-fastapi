# FastApi-playground
A FastAPI lab for prototyping ideas, testing features, and deepening API knowledge.

![Fastapi 8](https://github.com/user-attachments/assets/cf28c33f-eba2-4562-a1f8-ce02e09c1afa)

![Fastapi 7](https://github.com/user-attachments/assets/de5730b6-9fbe-4f2d-a061-c5eba6731f1d)

![Fastapi 6](https://github.com/user-attachments/assets/574a192d-2d68-4a30-af85-d6817e5bdf43)

![Fastapi 5](https://github.com/user-attachments/assets/08d4b9ec-d6ff-43ea-86cb-dd7061c71e3e)

![Fastapi 4](https://github.com/user-attachments/assets/380c1b44-e4ca-4c5e-af6d-47009bbad433)

![Fastapi 3](https://github.com/user-attachments/assets/21a25096-17e5-4288-b238-8dfe5c542ca2)

![Fastapi 2](https://github.com/user-attachments/assets/65a5d86e-b424-4d42-a9c8-154176f7fab9)

![Fastapi 1](https://github.com/user-attachments/assets/5bf32338-a69c-48b3-b597-fd32351ead8e)

## Why FastAPI is fast to code?

1. Automatic input Validation <br>
2. Auto-Generated interactive Documentation <br>
3. Seamless Integration with Modern Ecosystem (ML/DL libraries, OAuth, JWT, SQL Alchemy, Docker, Kubernetes etc) 

#### Run the Server:

```bash
uvicorn main:app --reload
fastapi dev app.py
```

## Request body:

A **request body** is the portion of an HTTP request that contains data sent by the client to the server. It is typically used to HTTP methods POST or PUT to transmit structured data (e.g. JSON, XML, form-data) for the purpose of creating or updating resources on the server. The server parses the request body to extract the necessary information and perform the intended operation.



## **HTTP Requests:**

## Real-world analogy:

GET is like reading a book in a library.
Post is like writing a note and handing it to the librarian.

-	When you GET, you’re just requesting to see something
-	When you POST, you’re sending data to be processed or saved.

### Technical Difference

| Feature | GET | POST |
| -------- | ------- | ------- |
| Purpose | Retrieve data | Submit data |
| Data location | In URL (query string) | In the request body |
| Visibility | Data is visible in URL | Data is hidden from URL |
| Use for | Reading/fetching resources | Creating/updating resources |
| Bookmarkable | Yes | No |
| Idempotent | Yes (repeating gives same result) | Not necessarily (can cause changes |

### Get request:

```http
GET /search?query=shoes HTTP/1.1
```

-	You’re asking: “Hey server, show me all the shoes.”

### POST request:

```http
POST /add-to-cart HTTP/1.1
Body: { “item_id”: 123, “quantity”: 2}
```

-	You’re saying: “Hey server, please add this item to my cart.”

## Think of it like a conversation with a website:

### 1. GET = “Just give me info”

-	You’re asking the server for something.
-	Example: “Show me all blog posts tagged with ‘travel’.”
-	You don’t change anything on the server.
-	The server responds with that info.

**In the browser: **

-	You type in a URL or click a link – that’s a GET request.
-	Example: `https://example.com/posts?tag=travel`

### 2. POST = “I’m giving you something to do”

-	You’re sending data to the server to do something with it.
-	Example: “Here is my comment on this blog post.”
-	The server might save that comment to a database.

**In the browser: **

-	You fill out a form and click “Submit” – that’s a POST request.
-	Example: You post a review, submit login info, or upload a photo.

## Why does it matter?

-	GET is for viewing. (safe, can be cached, can be bookmarked.)
-	POST is for doing. (Sends new data, not cached, not bookmarkable.)

## GET Scenarios (Read-only actions)

These are situations where the client just wants to retrieve data, without making any changes:

### 1. Loading a web page

-	URL: `https://news.com/latest`
-	You want to view the latest news.
-	No data is sent except in the URL.

### 2. Search queries

-	URL: `https://store.com/search?q=laptop`
-	You are searching for laptop”.
-	The search term is passed as a query string.

### 3. Viewing a user profile

-	URL: `https://site.com/user/john`
-	Just displays John’s profile
-	Doesn’t change anything.

### 4. Pagination

-	URL: `https://blog.com/posts?page=3`
-	You’re just asking for page 3 of the blog.

### 5. Filtering results

-	URL: `https://shop.com/products?category=shoes&price=low`
-	You’re applying filters to what you see.

## POST Scenarios (Write/Submit actions)

These are situations where the client is sending data to the server to create, modify, or trigger actions.

### 1. Submitting a login form

-	URL: `https://site.com/login`
-	Sends your username and password.
-	Server checks and starts your session.

### 2. Creating a new user/account

-	URL: `https://site.com/signup`
-	Sends your name, email, password, etc.

### 3. Submitting a contact form

-	Sends message, name, email to the server to be saved or emailed.

### 4. Uploading a file or image

-	Sends the file data as part of the request body.

### 5. Adding to a shopping cart

-	You click “Add to Cart” – the item ID and quantity are sent to the server.

### 6. Placing an order

-	URL: `https://shop.com/checkout`
-	Sends the cart items, payment detail, shipping info.

### 7. Posting a comment or message

-	Submits text, maybe with a post ID or thread ID.


## Summary Table:

 Scenario | Method |
 -------- | ------- | 
 View a blog post | GET |
 Search for a products | GET |
 Login to a site | POST |
 Sign up for a new account | POST |
 Add an item to cart | POST |
 Submit a contact form | POST |
 View a list of product | GET |
 Filter products by price | GET |
 Post a review | GET |
 Get weather info by city | GET |
 Upload a profile picture | POST |
 View user profile | GET |

## GET Request on Flipkart (Viewing or fetching data)

These happen when you’re just browsing or searching without changing anything on the server.

### 1. Homepage Load

-	When you go to `https://www.flipkart.com`, your browser sends a GET request.
-	You’re just asking to view the homepage.

### 2. Searching for a product 

-	You type “mobile phone” in the search bar and hit Enter.
-	URL becomes: `https://www.flipkart.com/search?q=mobile+phones`
-	That’s a GET request with the query `q=mobile+phones`
-	You are just requesting info.

### 3. Filtering products

-	Apply a filter like “Price: Low to High” or select a brand.
-	URL updates to something like: `https://www.flipkart.com/search?q=mobile+phones&sort=price_asc&brand=Samsung`
-	Still a GET request – just showing filtered results.

### 4. Viewing a product

-	Click on a phone to see its details.
-	URL: `https://www.flipkart.com/Samsung-galaxy/product-id`
-	Again, it’s just fetching info – so it’s a GET.

## POST Requests on Flipkart (Sending data or changing state)

These happen when you interact in a way that changes something – like logging in, adding to cart, or checking out.

### 1. Logging in

-	You enter your phone/email and password.
-	Your browser sends a POST request to `https://www.flipkart.com/api/login`
-	Flipkart checks your credentials and starts a session.

### 2. Adding a product to cart

-	You click “Add to Cart”.
-	A POST request is sent to something like: `https://www.flipkart.com/api/add-to-cart`
-	Data sent: `{ product_id: 12345, quantity: 1 }`

### 3. Placing an order

-	After selecting items, address, and payment, you click “Place Order”.
-	A POST request sends your order details to Flipkart’s servers to process.

### 4. Submitting a review

-	You rate a product and write a review.
-	Flipkart uses a POST request to store that review in their database.


### Path Parameter

The Path() function in FastAPI is used to provide, validation rules, and documentation hints for path parameters in your API endpoints.

Title <br>
Description <br>
ge, gt, le, lt <br>
Min_length <br>
Max_length <br>
regex <br>


### HTTP status codes

**HTTP status codes** are **3-digit number** returned by a web server (like FastAPI) to indicate the result of a client's request (like from a browser or API consumer).

LINK


They help the **client (browser, fronted, mobile app, etc.) understand**:

- whether the request was successful.
- whether something went wrong.
- and what kind of issue occurred (if any).

|  |  |  |
| -------- | ------- | ------- |
| 2xx | ✅ Success | The request was successfully recieved and processed |
| 3xx | 🔁 Redirection | Further action needs to be taken (e.g. redirect) |
| 4xx | ⚠️ Client Error | Something is wrong with the request from the client |
| 5xx | ❌ Server Error | Something went wrong on the server side |


|  |  |  |
| -------- | ------- | ------- |
| 200 OK | Standard success | A `GET` or `POST` suceeded |
| 201 Created | Resource created | After a `POST` that created something |
| 204 No Content | Success, but no data returned | After a `DELETE` request |
| 400 Bad Unauthorized | Malformed or invalid authentication | Missing field, wrong data type |
| 401 Unauthorized | No/invallid authentication | Login required |
| 403 Forbidden | Authenticated, but no permission | Logged in but not allowed |
| 404 Not Found | Resource doesn't exist | Patient ID not DB |
| 500 Internal Server Error | Generic failure | Something broken the server |
| 502 Bad Gateway | Gateway (like Nginx) failed to reach backend |  |
| 503 Service Unavailable | Server is down or overloaded |  |

`HTTPException` is a Special built-in exception in FastAPI used to **return custom HTTP error responses** when something goes wrong your API.

Instead of returning a normal JSON or crashing the Server, you can **gracefully raise an error** with:

- a proper **HTTP** stats code (like 404, 400, 403, etc.)
- a custom error message
- (optional) extra header


## Query Parameter

**Query parameter** are optional key-value pairs appended to the end of a URL, used to **pass additional data** to the server in an HTTP request. They are typically employed for operations like filtering , sorting. <br>
searching and pagination without altering the endpoint path itself.

`/patients?city=Delhi&sort_by=age`


- The `?` marks the start of query parameters.
- Each parameter is a key-value pair: `key=value`
- Multiple parameters are separated by `&`

In this case:

- `city=Delhi` is query parameter for filtering
- `sort_by=age` is a query parameter for sorting


`Query()` is a utility function provided by **FastAPI** to declare, validate, and document **query parameters** in your API endpoints.


## Pydantic

**1. Define a Pydantic model** that represents the **ideal schema** of the data.

- This includes the expected fields, their types, and any validation constraints (e.g. `gt=0` for positive number).

**2. nstantiate the model with raw input data** (Usually a dictionary or JSON-like structure).

- Pydantic will Automatically **validate** the data and **coerce** it into the correct Python type (if possible).
- If the data doesn't meet the model's requirements, Pydantic raise a `validationError`.

**3. Pass the validateed model object** to functions or use it throughout your codebase.

- This ensures that every part of your program works with **clean, type-safe, and logically valid data**.



### What is the difference between class and function in Python?

In Python, you use classes to describe objects. Think of a class as a tool you use to create your own data structures that contain information about something; you can then use functions (methods) to perform operations on the data you describe.




## Bash Environment Commands

- To Create a file

```bash

touch <file_name>
# Example: touch Test_Excercise.py
```

- Run python (.py) file:

```bash
python file_name.py

```

- To Create a virtual environment

```bash

python -m venv <env_name>
# Example: python -m venv mlapi
```

- Activate the virtual environment

```bash

source <env_name>/bin/activate  # for macos
source <env_name>/Scripts/activate  # for windows
# Example for macos: source mlapi/bin/activate
# Example for window bash: source mlapi/Scripts/activate
```
- Deactivate the virtual environment

```bash

deactivate
```

- Delete the environment

```bash

rm -rf <env_name>
# Example: rm -rf mlapi
```

- Useful Bash Tips for Environment Management

List Python virtual environments if stored in a folder (e.g., `~/venvs`)

```bash

ls ~/venvs
```

Find all virtual environments on your system (search for `activate` scripts)

```bash

find ~ -type f -name "activate"
```

Quick script to list venv env names inside `~/venvs`

```bash

for dir in ~/venvs/*; do
  if [ -f "$dir/bin/activate" ]; then
    echo "$(basename "$dir")"
  fi
done
```

## Pip Commands

- To install requirements.txt = `pip install -r requirements.txt`
- To check install packages = `pip list`
- To check detailed about package = `pip show package_name`
- To install package = `pip install package_name`
- To uninstall package = `pip uninstall package_name`
- To save all packages of env to a requirements.txt file = `pip freeze > requirements.txt`

## Git commands

- To add all file = `git add .`
- To add any particular file = `git add <file_name>`
- To commit = `git commit -m "commit message"`
- To push the code = `git push origin main`

Docs:

- Documentation: https://fastapi.tiangolo.com
- Source Code: https://github.com/fastapi/fastapi

-  Swagger UI:

```bash
localhost:8000/docs
http://127.0.0.1:8000/docs
```

