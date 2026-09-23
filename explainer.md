# How my contact form works

> Draft. Rewrite this in your own words before you hand it in. The brief checks that it's yours.

## What a backend is

My portfolio page is just files (HTML, CSS, a bit of JavaScript) that your browser downloads and shows. It can't do anything on its own after that. It can't store a message or send an email, because all of it runs on the visitor's computer.

A **backend** is a program on a server somewhere else that the page can send data to. The server can do the things a page can't: keep secrets like passwords and API keys, save data, and send emails. The page and the server talk over the internet using HTTP requests.

## What my feature does

The "Contact me" form lets a visitor type their name, email, and a message. When they click **Send**, the message arrives in my email inbox. I didn't write my own server for this. I use **Web3Forms**, a free service that acts as the backend for me.

## How the data flows

1. **The visitor fills in the form** on my page and clicks Send.
2. **My JavaScript stops the normal page reload**, collects the fields (name, email, message, and my access key), and turns them into JSON.
3. **The browser sends that JSON** in a `POST` request to `https://api.web3forms.com/submit`.
4. **The Web3Forms server checks the request.** It uses the access key to work out which account the message belongs to (mine), and it rejects the request if the hidden "botcheck" spam-trap box has been ticked.
5. **Web3Forms emails the message** to the address I signed up with.
6. **The server replies to the browser** with `success: true` or an error message.
7. **My page shows the result** to the visitor: "Thanks! Your message was sent" or "Sorry, that didn't send".

```
Visitor's browser  --(POST JSON)-->  Web3Forms server  --(email)-->  My inbox
        ^                                   |
        +--------(success / error)----------+
```

## Why the access key is safe in the page

The access key is visible to anyone who views the page source. That's fine, because it's not a password. It can only do one thing: send form messages to *my* inbox. It can't read my email or log in to anything.

## Free tier

Web3Forms is free for up to 250 submissions a month, which is plenty for a portfolio. The page itself is hosted free on GitHub Pages or Netlify.
