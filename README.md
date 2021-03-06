

# HTTP Requester

Perform HTTP & WS requests like a boss!

A command line utility that supports HTTP, HTTPS, Websocket and server creation.

It features a cool interactive shell.

Ideal for testing and debugging.

* License: MIT
* Current status: beta



### Install

Do not forget to install it **globally**:

```
npm install -g http-requester
```



### Feature highlights:

* HTTP, HTTPS and Websocket requests
* Dummy HTTP and Websocket server creation
* A cool interactive shell with history and auto-completion (even headers)
* An interactive Websocket Chatter



### *“Like a boss? Screenshot please!”*

![Screenshot](https://raw.githubusercontent.com/cronvel/http-requester/master/screenshot1.png)



### Available command line options:

* Without any argument, it runs the interactive shell
* --help, -h: display help
* --shell: run requests in an interactive shell, *like a boss!*
* --method <method>: set the HTTP method
* --protocol http|https|ws: set the protocol, 'http', 'https' or 'ws'
* --host <host>: set the targeted host
* --port <port number>, -p <port number>: set the targeted port, default is 80 (HTTP) or 443 (HTTPS)
* --path <path>: set the path of the targeted resource in the host
* --url <URL>: the full URL of the resource, will be splitted into protocol, host, port and path
* --headers.* <header value>: any header can be specified as an option, e.g. --headers.content-type application/json.
  If it is not conflicting with another options, it can be used without prefix,
  like --content-type application/json
* --headers <json string>: specify all headers using the JSON format
* --auth "<user>:<password>": basic authentication i.e. "user:password" to compute an Authorization header
* --timeout <ms>: set the request timeout in ms
* --output <file>, -o <file>: if given, the body's response will be written to this file instead of STDOUT
* --http: shortcut for --protocol http
* --https: shortcut for --protocol https
* --ws: shortcut for --protocol ws
* --beautify, -b: beautify JSON body
* --server: start a server
* --config <file>: a JSON file containing all the above options, structured in an object

**Syntactic sugar:**

* `http-requester` launch the interactive shell, like `http-requester --shell`
* `http-requester <file>` load a config file, like `http-requester --config <file>`
* `http-requester <url>` GET the url, like `http-requester --method get --url <url>`
* `http-requester <method> <url>` request the url, like `http-requester --method <method> --url <url>`



### Available interactive shell commands:

* **show** *or* **s**

	List the details of the request about to be performed.

* **request** *or* **req**

	Perform the request.
	
* &lt;protocol&gt;://&lt;host&gt;[:&lt;port&gt;][/&lt;path&gt;]

	Parse the full URL and set the protocol, host, port and path.

	E.g.: `> http://localhost:8080/blog/index.html`

* **host** &lt;hostname&gt;[:&lt;port&gt;]

	Set the host and port to connect to.

	E.g.: `> host localhost:8080`

* **port** &lt;port&gt;

	Set the port to connect to.

* **protocol** http|https|ws

	Set the protocol to use.

* **method** &lt;HTTP method&gt;

	Set the HTTP method.

* **cd** &lt;path&gt;

	Modify the path just like the shell 'cd' command does.
	Start the path with a '/' to set the absolute path, otherwise it moves relative to the current path.
	It does **NOT** modify the query-string part of the URL.

	E.g.: `> cd blog` , `> cd ..` , `> cd ../../blog/index.html` , `> cd /index.html` , ...

* **?** &lt;query string&gt;

	Set the query string part of the URL.
	Use a single `?` alone to erase the query string.

	E.g.: `> ?` , `> ?key=value` , `> ?key1=value1&key2=value2` , ...

* headers.&lt;header&gt; &lt;value&gt;

	Set a HTTP header.
	
	E.g.: `> headers.Content-type: text/html`

* &lt;header&gt;: &lt;value&gt;

	The shortest way to set a HTTP header.
	
	E.g.: `> Content-type: text/html`

* **auth** &lt;user&gt;:&lt;password&gt;

	Basic authentication to compute an Authorization header.

* **body** &lt;body string&gt;

	Set the body of the request.

* **body**

	Set the body of the request, using the multi-line mode.

* **timeout** &lt;ms&gt;

	Set the request timeout in ms.

* **clear** [headers|auth|body]

	Clear headers, auth or body, without argument: clear both.

* **autoclear** [headers|auth|body]

	Autoclear headers, auth or body after each request, without argument: just check.

* **autocookie**

	Turn autocookie on/off.

* **beautify**

	Turn beautify on/off for JSON body.

* **ls**

	List all known sub-resources of the current path, just like the UNIX 'ls' command does.




