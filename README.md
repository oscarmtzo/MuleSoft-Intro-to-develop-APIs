# MuleSoft - Connecting data to applications 

<a src="https://blogs.mulesoft.com/learn-apis/api-led-connectivity/what-is-api-led-connectivity/">API - Led connectivity</a> is a methodical way to connect data to applications through reusable and purposeful <a src="https://developer.mozilla.org/es/docs/Learn/JavaScript/Client-side_web_APIs/Introduction"> API </a> (available prebuild connection points for several programming languages) that allows developers create complex functionalities for an easy consumption when developing an application, not worring about what's going on under the hood, just the necessary means of connections like an electrical outlet on a wall.
<figure>
    <img src="https://mdn.mozillademos.org/files/14317/plug-socket.png" width="150px;" alt="electrical outlet"/> 
    <figcaption>Electrical outlet; source: MDN Web Docs. </figcaption>
</figure>

This notes embrace:
* What an application network is and its benefits.
* How to build an application network using API-led connectivity.
* An Explanation of what web services and APIs are.
* Making calls to secure and unsecured APIs.

----

**The usefulness of this for businesses**

The constant rate of change on IT require to levarage new ways to create assets to be consumed by business fast enough.


### Purpose of reausable assets
It is import for organizations the cycle of **production** as well as **consumption** of data for IT, either for own development of services or better fit the needs of consumers.

The main idea is that **data sources** are now needed to be accesible, flexible to grow, secure enough to continue  developing different applications regardless the numerous development of projects or the amount of time passed.


## API-Led connectivity mindset is:

* **Assets** have to be <a src="https://en.wikipedia.org/wiki/Composability" alt="Composability"> composable </a>; a highly composable system provides components that can be selected and assembled in various combinations to satisfy specific user requirements, in order to make reusable data.

<figure>
    <img src="https://blogs.mulesoft.com/wp-content/uploads/img_6059cf82c124c.png" width="350px">
    <figcaption>API-Led connectivity example</figcaption>
</figure>

## Center for enablement (C4E)
Ensures that assets are:
* Productized and published.
* Consumable.
* Consumable abroadly.
* Fully leveraged.

Is a cross functional team ensuring all new projects uses current assets and producing new ones when needed.  

## Achieveing an Application network
Within an organizations there are many different systems been used, legacy databases, social apps and many more, that are side loaded.

<figure>
    <img src="https://blogs.mulesoft.com/wp-content/uploads/2016/07/new-application_network_diagram-01.png" alt="node of networks by mulesoft" width="200px;"/>
    <figcaption>node of network</figcaption>
</figure>

## What is an API?
Stands for Application Programming Interface, they have existed since the advent of programming languages, from 50s to 60s and provide us the info for *how ro communicate with a software component*  but it could be referring to a number of things:
* API interface definition file (API specification).
    * Defines what you can call, what you send it, and what you get back.
* A web service.
    * Te actual API documentation you can make calls or to the interface of that API implementation.
* An API proxy
    * An application that controls access to a web service, restricting access and usage through the use of an API gateway.

## What is a web service?
Is a method of communication that allows two software systems to exchange data over the internet, with some rules required.
* **A web service API**: comprehensive description of how a client interacts with the web service.
* **The web serice interface implementing the API**: Is the code providing the structure to the application so it implements the API.
* **The web service implementation itself**: is the actual code and application.

### There are 2 main types of web services
* SOAP web services:
    * traditional, more complez type,
    * The communication rules are defined in an XML-based WSDL (Web services Description Languafe) file

* RESTful web services
    * Recent, simpler type.
    * Use the existing HTTP communication protocol.

### RESTful web services
Stands for Representational State Transfer.
It defines how systems comunicate using HTTTP protocol.

**HTTP** request method indicates which operation should be performed on the object identifies by the URL.
Examples of RESTful calls:
* (GET)/companies
* (GET)/companies?country=France
* (GET)/companies/3
* (POST)/companies with JSON/XML in HTTP body
* (DELETE)/companies/3
* (PUT)/companies/3 with JSON/XML in HTTP body

**GET** retrieves the current state of a resource in some representation (usually JSON or XML)

**POST** creates a new resource

**PUT** replaces a resource completely, if the resource doesn't exist, a new one is created

**PATCH** partially updates a resource, just submitted data

---

## Calling RESTful web services
Sources:
* American Flights web service
http://training4-american-ws.cloudhub.io/api/flights
* REST API Vimeo http://www.programmableweb.com/api/vimeo-rest-api 

Making a call to a RESTful API is posible using a client tool, such as <a src="https://www.postman.com/" alt="postaman oficial page">Postman </a>, <a src="https://www.postman.com/">Advnaced REST Client</a>, or <a src="https://curl.se/docs/manpage.html">cURL</a> a command line utility.

You can make calls to secure and unsecure APIs, here's the catch:
* **Unsecured APIs**, the API may be public and require no authentication.
* **Secured APIs**, the APImay be secured and require authentication
    * You may need to provide credentials and/or a token
    * Often a proxy is created to govern access to an API
    * We will call and then later create an API secured by credentials
    * You can also secure an API with other authentication protocols, such as OAuth, SAML, JWT and more.

This training will make calls to and create a secured API.

### Getting response from web service calls
* RESTful web services return HTTP status code with the response
* <a src="https://developer.mozilla.org/es/docs/Web/HTTP/Status" alt="HTTP status codes">The status code</a> provides client feedback for the outcome of the operation (succeded, failed, upadates), there are 55 HTTP codes.

* Using Advanced REST Client, will be making several calls to an unsecured API (an implementation), no need of token or authentication.
* Make GET, DELETE, POST and PUT calls
* Use ARC to make calls to a secured API (an API proxy), authentication is needed
* Using API console in an API portal to make calls to a managed API using a mocking service.
* Using the API console to make calls to an API proxy endpoint.

## Using Advanced REST Client to make GET requests to retrieve data
1. Open Advanced REST Client
2. Make sure the method is set to GET
3. Return to the course ``snippets.txt`` file.
4. Copy the URL for the American Flights web service: http://training4-american-ws.cloudhub.io/api/flights 
5. Return to Advanced REST client and paste the URL in the box that says Request URL, replacing any existing content.
<img src="./images/arc_get_input.png" width="300px"/>
6. Click the send button, you should get a response.
7. Locate the return HTTP status code of 200.
8. Review the response body containing flights to SFO, LAX, and CLE.
<img src="./images/succesful_response_http_code_200_american_flights.png" width="200px"/> 
9. Select Raw from the options menu in the response area
<img src="./images/raw_response_200.png" width="200px">
10. Click the Open parameters editor icon (the pencil) to the right of the URL
11. In the query parameters editor area that appears, click the Add button.
12. Set the parameters name to the destination and the parameter value to CLE then click Close.
<img src="./images/query_to_CLE.png" width="200px">
13. Click the Send request button, you should get just the flights to CLE returned.
14. Edit the query parameters again, click te Remove this parameter button next to the parameter to delete it then click Close.
15. Change the request URL to add a URI parameter to retrieve the flight with an ID of 3: http://training4-american-ws.cloudhub.io/api/flights/3 
16. Click the send button, you should see only the lfight with an ID returned.
<img src="./images/response_id_3_flight.png" width="200px"/>

**Make DELETE requests to delete data**
17. Change the method to DELETE.
18. Click the Send button, you should see a 200 response with the message Flight deleted
<figure>
    <img src="./images/deleted_flight.png" width="250px"/>
    <figcaption>DELETE HTTP method</figcaption>
</figure>

19. Remove the URI parameter from the request http://training4-american-ws.cloudhub.io/api/flights 
20. Click the send button; you should get a 405 response with the message Method not allowed
<figure>
    <img src="./images/not_allowed_405.png" width="250px"/>
    <figcaption>DELETE HTTP method not allowed</figcaption>
</figure>

**Make a POST request to add data**

21. Change the method to POST. 
22. Click the send button, you should get a 415 response with the message Unsupported media type
<figure>
    <img src="./images/post_415_not_allowed.png" width="250px"/>
    <figcaption>POST HTTP method unsupported media type</figcaption>
</figure>

23. Click the Add button in the header area.
24. Select Content-type in the resultant Header name drop-down menu.
25. Type app in the Header value field then select application/json.
<img src="./images/header_post.png" width="250px"/>

26. Select body tab.
27. Return to the course ``snippets.txt`` file and cop the vlue for American Flights API post body. 
```
{
  "code": "GQ574",
  "price": 399,
  "departureDate": "2016/12/20",
  "origin": "ORD",
  "destination": "SFO",
  "emptySeats": 200,
  "plane": {"type": "Boeing 747", "totalSeats": 400}
}
```

28. Return to Advanced REST Client and paste the code in the body text area.
<figure>
    <img src="./images/post_body_raw_input.png" width="250px"/>
    <figcaption>POST body raw input</figcaption>
</figure>

29. Click the Send button, you should see a 2021 Created response with the message Flight added (but not really).
<figure>
    <img src="./images/raw_response_not_really.png" width="250px"/>
    <figcaption>POST response, http response 201 - Created</figcaption>
</figure>

30. Return to the request body and remove the plane field and value from the request body.
31. Remove the comma after the emptySeats key/value pair 
<img src="./images/raw_.edit_post.png" width="250px"/>

32. Send the request, the message should still post succesfully.
33. In the request body, remove the  emptySeats key/value pair.
34. Delete the comma after the destination key/value pair

<figure>
    <img src="./images/emptySeats_post.png" width="250px">
    <figcaption>POST bad Request</figcaption>
</figure>
35. Send the request, you should see a 400 Bad Request response with the messageBad request.
<figure>
    <img src="./images/post_bad_request.png" width="250px">
    <figcaption>POST bad Request</figcaption>
</figure>

**Make a PUT request to update data**

36. Change the method to PUT. 
37. Add a flight ID of 3 to the URL.
38. Click the send button; you shouldget a 400 Bad Request.
<figure>
    <img src="./images/post_bad_request_2.png" width="250px">
    <figcaption>POST bad Request</figcaption>
</figure>

39. In the request body field, press Cmd+Z or Ctrl+Z until the emptySeats field is added back.
40. Send the request; you should get a 200 OK response with the message Flightupdated (but not really).
<figure>
    <img src="./images/put_success_id.png" width="250px">
    <figcaption>PUT succesful http method</figcaption>
</figure>

**Make a request to a secured API**

41. Remove the Content-Type header by selecting the Headerstab then clicking the Remove this parameter buttonnext to the header.
42. Change the method to GET. 
43. Change the request URL to http://training4-american-api.cloudhub.io/flights/3 .

*Note: The -ws in the URL has been changed to -apiand the /api removed.*

44. Click the send button; you shouldget a 401 Unauthorized response with themessage Invalidclientidor secret.

<figure>
    <img src="./images/401_unathorized.png" width="250px">
    <figcaption>401 unathorized response</figcaption>
</figure>

45. Return to the course ``snippets.txt`` file and copy the value for the American Flights API client_id.
```
* American Flights API client_id for APDev fictitious application
d1374b15c6864c3682ddbed2a247a826
```
46. Return to Advanced REST Client and add a header called client_id.

47. Set client_id to the value you copied fromthe snippets.txtfile.
48. Return to the course ``snippets.txt`` file and copy the value for the American Flights API client_secret.
49. Return to Advanced REST Clientand add a second headercalled client_secret.
```
* American Flights API client_secret for APDev fictitious application
4a87fe7e2e43488c927372AEF981F066
```
50. Set client_secret to the value you copied fromthe snippets.txtfile.

<figure>
    <img src="./images/headers_modified.png" width="250px">
    <figcaption>Custom headers on Advanced REST Client </figcaption>
</figure>

*Note: The client credentials in the snippets file may be different than what is shown here; the values in the snippets file differ for instructor-led and self-study training classes.*

51. Click the send button; you should get data for flight 3 again.

<figure>
    <img src="./images/custom_headers_200.png" width="250px">
    <figcaption>Response to Custom headers on Advanced REST Client </figcaption>
</figure>

52. Click the send button several more times; you shouldget a 429 Too Many Requests response with the message Quota has beenexceeded.

*Note: For the self-study training class, the API service level agreement (SLA) for the application with your client ID and secret has been set to allow three API calls per minute while, for the instructor-led class, the SLA allows for a higher number to accommodate shared use.*

<figure>
    <img src="./images/too_many_responses.png" width="250px">
    <figcaption>Too many responses</figcaption>
</figure>

### Using the API console in the API portal to make requests to the API using a mocking service

53. Return to the browser window with the American Flights API portal at https://anypoint.mulesoft.com/exchange/portals/muletraining.
54. In the left-side navigation click the GET method for /flights.
55. Review the Headers and Responses sections.
56. In the Responses section, look at the output example.
57. In the API console located on the right side of the page, make sure the Mocking Service endpoint is selected.

58. Look at the endpoint URL that isdisplayed.59.Selectthe Show optional parameters checkbox.
60. Select LAX in the destination drop-down menu.
61. Enterany valuesforclient_idand client_secret.
62. Click Send; you should getthe example flights that areto SFO and ORD.

<figure>
    <img src="./images/request_API_portal.png" width="100px">
    <img src="./images/response_200_.API_portalpng.png" width="100px">
    <figcaption>API console for retrieving data</figcaption>
</figure>

**Makerequests to the API using an API proxy endpoint**

63. At the top of the API console, change the endpoint to Production –Rate limiting SLA based policy.
64. Look at the endpoint URL that is displayed.
65. Click Send; you should get a 401 Unauthorized response.
<img src="./images/proxy_response_query_API_portal.png" width="400px">

66. Copy and paste the client_id and client_secret values from the course ``snippets.txt`` file. 
```
* American Flights API client_id for APDev fictitious application
d1374b15c6864c3682ddbed2a247a826

* American Flights API client_secret for APDev fictitious application
4a87fe7e2e43488c927372AEF981F066
```

67. Click Send; you should get a 200 OK response with only flights to LAX.
<img src="./images/proxy_success_200.png">
