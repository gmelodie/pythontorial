# Week 3: HTTP

So remember HTML files? The ones with `<head>` and `<body>` tags we saw last week? Well HTTP, HyperText Transfer Protocol, is a protocol (a set of rules and standards) that tells us how to transfer HTML files across the internet.

There's a lot to tell about HTTP, but for now we'll be focusing on **URLs** and **methods**. **URLs** are the resource locators we saw on the first week (things like `http://google.com/`, now you know what the `http` stands for!). **Methods**, or *verbs*, are a way of telling people what you want to do. Here's a simple HTTP **request**:

```http
GET / HTTP/1.1
Accept: */*
Accept-Encoding: gzip, deflate
Connection: keep-alive
Host: example.com
User-Agent: HTTPie/2.3.0


```

A few things to notice here:
1. The `GET` right in the beginning is the method, it tells whoever we're sending this to (in this case `http://example.com`) that we want to *get* the file that's on the path `/` (which is short for `/index.html`).
2. The other fields (`Accept`, `Accept-Encoding`, `Connection`, `Host` and `User-Agent`) are the **request headers**. They are very important and we'll cover them in more detail later.
3. The `HTTP/1.1` part on the first line specifies the HTTP version we are using. In this case, `1.1`.
4. There are always two blank lines (two `\n`s) at the end of an HTTP message.


Now if there are **requests**, there must be **responses**. In this case we are requesting an HTML page, so ideally the response will be this very HTML page:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Age: 513099
Cache-Control: max-age=604800
Content-Encoding: gzip
Content-Length: 648
Content-Type: text/html; charset=UTF-8
Date: Wed, 27 Jan 2021 17:49:16 GMT
Etag: "3147526947"
Expires: Wed, 03 Feb 2021 17:49:16 GMT
Last-Modified: Thu, 17 Oct 2019 07:18:26 GMT
Server: ECS (agb/A436)
Vary: Accept-Encoding
X-Cache: HIT

<!doctype html>
<html>
<head>
    <title>Example Domain</title>
    ...
```

You can see the response is not *only* the HTML, but there's some more information. We won't care too much about all that metadata now, but it's important that you know it's there.


## Challenge

Python has a bunch of ready to use modules both built-in (that are officially supported by Python's core development team) and from the community. The [`requests`](https://requests.readthedocs.io/en/master/) library (or module) is a very powerful and popular tool to work with HTTP. Your task is to write a program that takes an URL, and gets the page it points to.

1. [Download and install the `requests` module](https://pypi.org/project/requests/)
2. Import the module in your code with `import requests`
3. Get the URL from the input (either from the [`sys.argv`](https://www.geeksforgeeks.org/how-to-use-sys-argv-in-python/) or from a regular `input` statement)
4. Issue a `GET` request with the `requests` library
5. Print only the HTML of the response.


Example:
```sh
$ python3 get_http.py example.com

<!doctype html>
<html>
<head>
    <title>Example Domain</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <style type="text/css">
    body {
        background-color: #f0f0f2;
        margin: 0;
        padding: 0;
        font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
...
```

**Bonus**: Check if the URL is valid using your URL parser and, if not, warn the user.


## Extra

1. Notice that in all the examples the `User-Agent` is [`HTTPie`](httpie.org/)? That is an HTTP tool to send, receive and analyze HTTP requests and responses. [Check it out](httpie.org/)!

2. We've talked about one of the HTTP methods (`GET`), but there are several others. Research about and play around (using HTTPie or the `requests` library) with the `POST` method.
