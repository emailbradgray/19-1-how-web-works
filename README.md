# 19-1-how-web-works

Good Resource : https://github.com/alex/what-happens-when

Part 1:
- What is HTTP?
    
    Hyper Text Transfer Protocol is governs how clients get data from, or send data to, a server.
    
- What is a URL?
    
    Short for Uniform Resource Locator, a URL is an address for some internet resource.
    
- What is DNS?
    
    Short for Domain Name System, this is a system that takes human-readable URLs and converts them into IP addresses.
    
- What is a query string?
    
    The query string allows you to pass key-value pairs into the URL, in the format `?key1=value1&key2=value2...`
    
- List two HTTP Verbs and their use cases.
    - GET - get some data from the server (most pages, search forms)
    - POST - send some data to the server (pages that change data on server)
- What is an HTTP request?
    
    An HTTP request is a request from a client to a server which follows the HTTP protocol (eg a request for HTML from news.google.com)
    
- What is an HTTP response?
    
    An HTTP response is a response from a server to a client which follows the HTTP protocol (eg sending back HTML/CSS/JS/etc)
    
- What is an HTTP header? Give a couple examples of request and response headers you have seen.
    - Headers provide additional information about the request or the response. Here are some examples:
    - Request headers: Host, User-Agent, Accept, Cookie, Cache-Control
    - Response headers: Content-Type, Last-Modified, Set-Cookie, Cache-Control
- What happens when you type a URL in a browser?
    1. Your browser “resolves” the name into an IP address using DNS
    2. Your browser makes a request to that IP address, including headers (info about browser, any previous cookies, and other things)
    3. The server sends a response (typically, HTML, with a status code (200 if it was sucessful)
    4. The browser makes a DOM from that HTML, and finds any other resources needed (images, CSS, JavaScript, etc)
    5. The browser makes separate HTTP requests for those resources and receives response from the server for each
  
  Part II. Use Curl 
  
  1. Using ***curl***, make a ***GET*** request to the *icanhazdadjoke.com* API to find all jokes involving the word “pirate”
  ~$ curl https://icanhazdadjoke.com/search?term=pirates
Why are pirates called pirates? Because they arrr!
Why do pirates not know the alphabet? They always get stuck at "C"

2. Use ***dig*** to find what the IP address is for *icanhazdadjoke.com*
dig icanhazdadjoke.com

; <<>> DiG 9.18.1-1ubuntu1.2-Ubuntu <<>> icanhazdadjoke.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 12142
;; flags: qr rd ad; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 0
;; WARNING: recursion requested but not available

;; QUESTION SECTION:
;icanhazdadjoke.com.            IN      A

;; ANSWER SECTION:
icanhazdadjoke.com.     0       IN      A       104.21.66.15
icanhazdadjoke.com.     0       IN      A       172.67.198.173

;; Query time: 9 msec
;; SERVER: 172.28.160.1#53(172.28.160.1) (UDP)
;; WHEN: Mon Mar 27 11:35:44 CDT 2023
;; MSG SIZE  rcvd: 86

Part 3. 
Make a simple web page and serve it using ***python3 -m http.server***. Visit the page in a browser.
Used liveServer in VSCode for memeGenerator

## **Part Three: Explore Dev Tools**

Build a very simple HTML form that uses the GET method (it can use the same page URL for the action) when the form is submitted.

Add a field or two to the form and, after submitting it, explore in Chrome Developer tools how you can view the request and response headers.

Edit the page to change the form type to POST, refresh in the browser and re-submit. Do you still see the field in the query string? Explore in Chrome how you can view the request and response headers, as well as the form data.



## **Part Four: Explore the URL API**

At times, it’s useful for your JavaScript to look at the URL of the browser window and change how the script works depending on parts of that (particularly the query string).

[Read about the URL API](https://developer.mozilla.org/en-US/docs/Web/API/URL)

Try some of the code examples in the Chrome Console so that you can get comfortable with the basic methods and properties for instances of the URL class.
