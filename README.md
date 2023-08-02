
# Handle Error in ASP.NET Core

With Asp.net core we can handle our errors in 3 levels. 

* Action 

* Controller

* App

## What does DeveloperExceptionPage MiddleWare do?


   

>  Stack Trace:

 - It is a trace mechanism that occurs at the time of an error.
 -  It shows the method where the error occurred and other methods that were
   called. 
 - It is important for debugging and identifying the source of
   the error.

> Query String Parameters:

* Key-value pairs added to the URL.
* Used to send data to the server.
* They start with "?" at the end of the URL and are separated by "&".

> Cookies:

 - Small pieces of data stored between the browser and the server.
 - Websites use them to store user preferences, session information.
 - They should be used carefully for privacy and security.

> Headers :

HTTP Headers (Hypertext Transfer Protocol Headers) are meta-information used in communication between browsers and servers through HTTP requests and responses. In each HTTP request or response, header fields are presented as key-value pairs and are used for specific purposes.

 1. Request Headers: Contains the details of the request sent from the browser to the server.

2. Response Headers: Contains the details of the response sent from the server to the browser.

3. General Headers: General headers that apply to both the request and the response.

4. Entity Headers: Used to identify and process HTTP entities (e.g. text, images, files).

> Example: "Content-Type: application/json" header indicates that the
> content coming from the server is in JSON format

5. Caching: HTTP headers are used for content caching between the server and the browser.

6. Language Preference: The "Accept-Language" header is used for the user's preferred language.

7. Authentication: The user can send authentication information with the "Authorization" header.

8. Security: The use of HTTPS encrypts the communication between the browser and the server and increases security.

9. Privacy: Headers such as the "Cookie" header are used to protect user privacy.

## What is Middleware Operation Logic?

Middleware is a software component used in the working logic of software applications to facilitate communication between client and server and to manage operations between application layers. It is frequently used especially in web applications and server-based systems.

> Request----------[DeveloperExceptionPage]---------------[ExceptionHandler ]---------------StatusCodePages------------------------------------------------->Response

1. Request Reception: Requests from the client are forwarded to the server and the middleware layer receives these requests.

2. Processing and Routing: Middleware uses predefined rules and functions to process incoming requests. Based on the request content, it determines the relevant operation or function and routes the request to the application layer.

3. Preprocessing and Postprocessing: Middleware preprocesses and postprocesses the request and response data before forwarding the request to the application layer or sending responses from the server back to the client. For example, converting the data format, compressing the data or performing security checks.

4. Business Logic: Middleware processes requests, separating business logic operations from the application layer if necessary. This allows the application code to be cleaner and more modular.

5. Response Generation: Middleware takes the results returned from the application layer and converts them into an appropriate response format to send to the client.

6. Sending Response: Middleware sends the generated response to the client and completes the process.

> Asp.net Core has 3 different environments. These environments come by
> default. You can create custom environments.
> ***Production:*** Production environment is the environment that is ready for live use and accessed by real users. This environment contains the  structure of the application that requires high performance, security and stability. The most appropriate configurations and bug fixes for the production environment should be used here.
> 
> ***Development:*** The development environment is where the application is  actively developed and debugged. This environment contains the configurations and behaviors to be used during the development of the application. For example, features such as enabling debug mode or reporting bugs in more detail can be active in the development environment.
> 
> ***Staging:*** The staging environment is the environment where final testing and checking of configurations is done before the application goes live. In this environment, settings similar to the configurations and behaviors that will be used in production can be used. This way,  more realistic results can be obtained about how the application will  behave before going live.

`UseExceptionHandler` **Middleware**

Redirects users to an error page when you get an error in your application.

`StatusCodePages()` **Middleware**

When you make a request to a page, it returns a status code for that page. 

`DatabaseErrorPage()` **Middleware**

If you are connecting to the db using the Entity framework, if an error occurs on the EF side, it gives more detailed information about this error.  

    ExceptionFilterAttribute Filters

Filters are important building blocks used in web application frameworks such as ASP.NET MVC and ASP.NET Core to process HTTP requests and organize responses. 

They are interfaces.

### What Does Filter Do?

* When a request comes to a method in a controller, we can handle the incoming request thanks to these filters before this request arrives, or when we get a response from a method in a controller, we can capture these responses thanks to these filters. 

* ***Authorization Filter:*** When you apply this filter on a controller or method basis, as an attribute, when a request comes to our code in the controller, we analyze whether this request is authorized to enter this method before entering the method.

* ***Action Filter:*** You can intervene before or after a method in the controller runs. After the method is finished, you can log when there is a structure you want to log.  

* ***Result Filter:*** It is used to edit the output generated as a result of the execution of a method or to perform extra operations.

* ***Exception Filter:*** Used to handle errors that occur during a client request.
