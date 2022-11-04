
# Explain how Node.js is better than Python and PHP. Why is it used so widely? What is body-parser and why is it used? 

As my interest lies in the second question, I will address it first


## Question - What is a body-parser and why is it used? 

<b>Answer</b> - Prior to answering your question, I'd like to clarify that no one uses the body parser anymore and if someone does, they're probably old or do not know express because express has its own body-parser as a middleware
method.

```express.json()```

Based on the body-parser library, this method works as expected. 
First, let me give you an example of what will happen if you don't use a body parser or express method.

```
const express = require("express");
const app = express();

app.post("/", (req, res) => {
 console.log(req.body);
 res.send("Post Request");
});

app.listen(3000, console.log("Server is running on Port 3000"));
``` 

- Here is basic server setup on which you are making a post request and logging out the result  ( req.body ). 
- Let’s run the server and make a request.
![post_req](https://user-images.githubusercontent.com/94318094/199997868-cf2893c7-2f98-488b-b07f-621e7fb10100.png)
- As you can see the post request is successful but the log result is undefined.
- The answer is simple you did not parse the upcoming JSON.

## Solution

- There are two ways to solve this problem: one is to use a library called body-parser or to use express's built-in middleware  “express.json” to parse the upcoming JSON data

```
const express = require("express");
const app = express();
 
app.use(express.json())
 
app.post("/", (req, res) => {
 console.log(req.body);
 res.send("Post Request");
});
 
app.listen(3000, console.log("Server is running on Port 3000"));
```

- Run the server 

![post_request_2](https://user-images.githubusercontent.com/94318094/199997979-f4f10a8e-fb77-42f7-901c-a560fc150a15.png)

- Now you can see the result successfully.

## Summary

The body-parser or express.json( which is based on body-parser ) is used to parse the upcoming JSON data and if you don’t parse the upcoming you can’t destructor the values in req.body.

---

Time to answer the first question
## Q . Explain how Node.js is better than Python and PHP. Why is it used so widely? What is a body-parser and why is it used?

Let's first divide the question into two sections to understand it better
- How Node.js is better than Python and PHP?
- Why is it used so widely


 <b>Note</b> - Speed, scalability, and performance are the three parameters used in the comparison

- Node.js uses a v8 engine to convert the javascript code into machine code. In a sense, V8 is like an interpreter that converts script code to machine code. You can refer to the v8 documentation for further details 
- In contrast to Python and PHP, Node.js supports a multi-threaded architecture and can handle multiple incoming requests at the same time. This makes the program more scalable than both ( Event-driven architecture is a story for another day ).

In light of these two points, you can now see why node.js is more efficient than python and PHP since it utilizes a v8 engine, follows an event-driven architecture which makes it more scalable, and it can deal with real-time events.

---

## Why it is used widely?

<b>Answer</b> - Why it should not be used widely, With its fast performance, high scalability, and scalability, it is the perfect solution. In contrast, node js is used by many big companies like Netflix, LinkedIn, and Uber because it is more productive, scalable, and performs better than other programming languages.

---

## Conclusion

Hopefully, I have answered all your questions fairly well, and I hope you are satisfied with my responses.
