# Introduction 
    Ramesh Kumar Dahiya
    Experince - 11+ in Software Development
    http://rkd.co.in
    @phpreboot
    @dahiyabecomp

# Best Practices
    1. Always use nouns , but no verbs
    E.g: 
  | resource   | Get                     | Put                 | Post                 | Delete              |
|------------|-------------------------|---------------------|----------------------|---------------------|
| /cars      | get list of call cars   | create a new car    | bulk update all cars | delete all cars     |
| /cars/{id} | get specific car detail | update specific car | method not allowed   | delete specific car |



# Whats WRONG !!
- /addNewEmployee
- /updateEmployee
- /deleteEmployee
- /deleteAllEmployees
- /promoteEmployee
- /promoteAllEmployees


# Dont use states in Get
E.g: 
- /cars/?set_activate=true
- /user/activate

# Use pural forms
E.g:
- /cars instead of /car
- /settings instead of /setting


# Version your API
- will be covered in next time

# Use HTTP status code
- 200 – OK – Eyerything is working
- 201 – OK – New resource has been created
- 204 – OK – The resource was successfully deleted

- 304 – Not Modified – The client can use cached data

- 400 – Bad Request – The request was invalid or cannot be served. The exact error should be explained in the error payload. E.g. „The JSON is not valid“
- 401 – Unauthorized – The request requires an user authentication
- 403 – Forbidden – The server understood the request, but is refusing it or the access is not allowed.
- 404 – Not found – There is no resource behind the URI.
- 422 – Unprocessable Entity – Should be used if the server cannot process the enitity, e.g. if an image cannot be formatted or mandatory fields are missing in the payload.
- 500 – Internal Server Error – API developers should avoid this error. If an error occurs in the global catch blog, the stracktrace should be logged and not returned as response.

# Resource
- anything which have some associate date and on which someone can operate the data

# COllection
- Collection of resource , e.g Users , Companies
# Diff between resource and sub resource 
- /cars - resource
- /cars/driver - sub resources
- /companies/1/employees
- /cars?type=driver wrong intrepretation

# Headers


| Header     | Description                   | Example   |
|------------|-------------------------|---------------------|----------------------|---------------------|
| Accept	| Content-Types that are acceptable for the response	| Accept: text/plain
| Accept-Charset | 	Character sets that are acceptable	| Accept-Charset: utf-8
| Accept-Encoding	| List of acceptable encodings	| Accept-Encoding: gzip, deflate
| Accept-Language	| List of acceptable human languages for response	| Accept-Language: en-CA
| Cookie	| an HTTP cookie previously sent by the server with Set-Cookie |	Cookie: $Version=1; Skin=new;
| Content-Length | 	The length of the request body in octets (8-bit bytes)	| Content-Length: 348
| Content-Type | 	The MIME type of the body of the request (used with POST and PUT requests)| Content-Type: application/x-www-form-urlencoded
| Authorization | 	Authentication credentials for HTTP authentication |	Authorization: OAuth realm="http://sp.example.test/",

# Accept Encoding
- Accept-Encoding: gzip
- Accept-Encoding: compress
- Accept-Encoding: deflate
- Accept-Encoding: br
- Accept-Encoding: identity

accept-language:en,de;q=0.8,en-US;q=0.6

# Cache request directives
- Cache-Control: max-age=5
- Cache-Control: max-stale=5
- Cache-Control: min-fresh=5
- Cache-Control: no-cache 
- Cache-Control: no-store
- Cache-Control: no-transform
- Cache-Control: only-if-cached

# Cache response directives
- Cache-Control: must-revalidate - verify and not use expiered data
- Cache-Control: no-cache - submit request to origin server before releasing
- Cache-Control: no-store - not store anything about request or response
- Cache-Control: no-transform
- Cache-Control: public - for all
- Cache-Control: private - for specific user
- Cache-Control: proxy-revalidate
- Cache-Control: max-age=5 - max age till data remain fresh

# oAuth 2.0
-  Auth Roles
    - Resource owner 
    - Resource server
    - Client
    - Authorization server

# Authorization Grant types
- Authorization Code - used with server-side Applications , e,g facebook
- Implicit - token within the response url
- Password Credentials - user credentials wiht client id
- Client Credentials