# Week 2: HTML

HTML, HyperText Markup Language, is a language ( **not a programming language** ) we can use to create rich text. That is, text that contains more than just words and punctuation. In HTML we can create pages with images, bold/italic text, videos and, more importantly here for us, **links** to other pages (you know, those things you can click on that take you to another place on the web).

HTML is all about tags, tags must be opened, like in `<head>` or `<body>` and closed (`</head>`, `</body>` respectively). Also, tags can be nested, so you can have tags inside of other tags.


## Challenge

Write a simple HTML parser, very similar to the last challenge, that checks whether an HTML file is valid or not. Output should be either `True`, if the HTML is valid or `False` otherwise.

Here's an example of valid HTML:
```html
<html>
    <body>
        <h1> H1 is a Header (title) </h1>
        <h2> H2 is a bit smaller than H1 </h2>
        <p>
            Paragraphs are made with this tag and <strong>bold is made with the strong tag</strong>.
        </p>

        Now pay very close atention, <a href="https://www.google.com/search?hl=pt&q=what%20is%20a%20tag%20in%20html">this</a> is the most important part. Got it?
    </body>
</html>
```

Don't worry about supporting each and every HTML tag, focus on the most important ones: `html`, `body`, `head`, `a`, `p`, `strong`, `h1`, `h2` and `div` are enough for us here.

Important things to remember:

1. The same tag cannot appear inside itself (e.g. `<h1> hello <h1> omg </h1> </h1` is invalid)
2. Tags have hierarchy (e.g. `<body>` cannot appear inside `<p>` tags just as `<html>` cannot appear inside any other tag), you'll have to keep track of that.
3. For the tags we are supporting here, all of them must be closed. Be careful with things like `<p> hello <strong> there </p> </strong>`. This is invalid! `<strong>` must be closed before `<p>` is closed.


