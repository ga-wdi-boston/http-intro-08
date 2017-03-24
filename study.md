# HTTP Study

Read this document entirely. Follow any links and study their content. Readings
and activities are **required** unless otherwise indicated.

## HTTP Required Reading

HTTP is a protocol - a system of rules - that determines how documents are
transferred from one place to another. Among other things, it defines the format
of the messages passed between *clients* and *servers*.

"Clients" send *requests* and receive *responses*. Examples include browsers
(like Chrome, Safari, or Firefox) and other programs like
[`curl`](http://curl.haxx.se/docs/) and
[`wget`](http://www.gnu.org/software/wget/manual/wget.html).

"Servers" receive requests and send responses. Examples are more complex, since
there are different kinds of servers. There are application servers, which work
in Node or Ruby to generate documents using those languages, and there are web
servers like [Apache](http://httpd.apache.org/), [nginx](http://nginx.com/), and
[lighttpd](https://www.lighttpd.net). The word "server" is also used to describe
the machine that these programs run on. In this document, the latter is what we
mean when we say "server", as in this diagram:

> ![http-xkcd](https://cloud.githubusercontent.com/assets/388761/12621764/0ffb527e-c4f0-11e5-87ae-d597e3835fcd.png)
>
> [Symfony and HTTP Fundamentals (The Symfony Book)](http://symfony.com/doc/current/book/http_fundamentals.html)

1.  A client sends a request to a server.
1.  The server processes the request.
1.  The response gets sent back to the client.
1.  The client processes the response.

## URLs

Which server is the request sent to? How does the server know what to respond
with? Both of these questions are answered by *uniform resource locator (URL)*.

> ![URL](https://cloud.githubusercontent.com/assets/388761/12622184/2c0143dc-c4f2-11e5-84af-55f723dd6639.png)
>
> unknown source

Study each part of a URL using the [Mozilla Developer Network
Documentation](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL).

## HTTP Verbs

A request has two parts: a URL and a verb. A request without both is incomplete.

By default, the browser issues GET requests when you type a URL into the address
bar and press `enter`. When you submit forms, the browser typically issues a
POST request.

-   [A Beginner’s Guide to HTTP and REST - Envato Tuts+ Code Tutorial](http://code.tutsplus.com/tutorials/a-beginners-guide-to-http-and-rest--net-16340)
-   [HTTP Methods for RESTful Services](http://www.restapitutorial.com/lessons/httpmethods.html)

## Make a Request

Make a request using the browser. Go to [Google](https://www.google.com). When
you clicked this link, the browser made a GET request to Google's server. We
often describe requests like this:

```txt
GET https://www.google.com/
```

If we know we're working with a particular server, we might abbreviate
it as follows. For example, if Google had API documentation that described
requests you could make to its server, that documentation might say instead:

```txt
GET /
```

In other words, API docs often only describe the URI instead of the full URL.

The response your browser receives from Google is an HTML document the browser
parses and renders. What would happen if you made the same GET request outside
of the browser?

Try this in your terminal:

```sh
curl --request GET https://www.google.com
```

What did you see?

## Responses & Resources

Servers send responses, and those responses contain resource representations.

Technically, the term "resource" refers to an abstraction that your application
uses; depending on what the application does, a resource might be a 'Car', a
'Person', a 'User', or an 'Order Cart'.

A single resource can be represented in multiple different ways by the server,
including HTML, JSON, PDF files, and images. What we really mean when we say
"resource" above is a specific representation of a resource.

You may think of resources as the documents that are returned (usually HTML or
JSON) as part of the response body.

## Response Statuses

What are HTTP status codes?

-   [List of HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
-   [HTTP Status Codes in a Nutshell](https://twitter.com/stevelosh/status/372740571749572610)

## Videos

1.  [Basic concepts of web applications, how they work and the HTTP protocol](https://www.youtube.com/watch?v=RsQ1tFLwldY)
1.  [Know about HTTP URL](https://www.youtube.com/watch?v=ADQ_rhefgEk)
1.  [Understanding HTTP Request Response Messages](https://www.youtube.com/watch?v=sxiRFwQ1RJ4)

## Additional Resources

-   [Conquering the Command Line: `curl`](http://conqueringthecommandline.com/book/curl)
-   [Media Types](http://en.wikipedia.org/wiki/Internet_media_type)

## Questions

Use your favorite search engine and the provided readings to research and
respond to the following questions.

In your responses, be sure to cite any relevant sources you consulted in your
search. We ask you to write responses in your own words in order to see how you
process what you've read. Please do not respond with direct quotes from source
material. Instead, digest what you've read and repeat it in your own voice.

## Define HTTP

In your own words, give a brief description of what HTTP is.

HTTP stands for Hypertext Transfer Protocol. HTTP is a specially formatted message that clients and servers use to communicate with each other or to transfer and exchange hypertext. It is the foundation for data communication on the Web.

## Describe what a client is and what a server is

 What is a client and what is a server? How do they interact with each other?

A client is the computer that is attempting to access information on a server. A server is a device or program that provides the data in which clients are attempting to access. A client will send the server a request for a particular resource using HTTP. Common HTTP methods are get(retrieve a resource from the server), post(create a resource on the server), put/patch(update resource on the server), and delete(remove resource on the server). Once the server recieves the request it prepares the resource via the URI and sends the server back a HTTP response containing the requested resource (e.g. HTML) and a status code detailing any issues with the request and response. Finally the client processes the response.

## Describe the 4 most common HTTP verbs

What are the 4 most common HTTP verbs used when creating a RESTful API. How
would you use each?

The four most common HTTP verbs are as follows:
  Get: Retrieves a particular resource from a server
  Post: Create a resource on the server
  Put/Patch: Updates a resource on the server
  Delete: Removes a resource from the server

## Describe what a Response is

What is a response? What does it contain? What are some common status codes in a
response and what do they mean?
A response is the HTTP message sent by the server to the client after it processes the client's request. The response contains a status line which contains the protocol version followed by a numeric Status-Code. The Status-Code details any issues or notes with the request and response. Status-Codes are followed by a reason phrase which gives a short textual description of the Status-Code. Common status codes are 200 OK (standard response for HTTP requests), 201 Created (new resource was created), and 204 No Content (the server successfully processed the request but is not returning any content).



## Make a curl request

Using curl, how would you get the content from Reddit.com?

Curl must first be installed on the system. Then, in the command line type 'curl -O https://www.reddit.com/'. The -O (uppercase o) downloads all of the files as the same name of the files on the website.

## Describe the parts of a URL

List the parts of a URL and explain what each part is, in your own words. You'll
refer to this list often in the next few weeks, so it's important to keep it in
an easy-to-reference place.

used https://www.mattcutts.com/blog/seo-glossary-url-definitions/

http://video.google.co.uk:80/videoplay?docid=-7246927612831078230&hl=en#00h02m30s

- The protocol is HTTP
- Hostname is video.google.co.uk
- The subdomain is video
- The domain name is google.co.uk
- Top level domain: uk
- Second level domain is co.uk
- The port is 80, the default value for web servers
- The path is /videoplay. Refers to location of file on server
- The parameters are 72469....
- The fragment or named anchor is #00h02m30s. Used to refer to an internal section of the web document.
