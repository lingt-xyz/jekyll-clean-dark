---
layout: post
title: Why trailing slashes on uris are important
mathjax: false
comments: false
share: false
mathjax: false
tags:
- network
---

### Origin of the trailing slash

In Unix, a trailing slash on a pathname identifies the path as pointing to a folder (aka directory). If a pathname does not have a trailing slash then it points to a file. A folder is a ‘collection’ of files.

<!--more-->

The syntax of URIs is derived from the syntax of Unix filenames, and the concept of using trailing slashes to identify ‘collection’ resources was carried over. However on the Web, the strong delineation between folders and files does not exist, frequently a ‘collection’ resource appears similar in structure and content to a normal resource (sometimes referred to as a ‘subordinate’ resource).

### Relative URIs 
#### Doing it wrong

|     Base URI    |   Relative URI  | Absolute URI   |
| ------------- |-------------| -----|
|[http://some-blog.io/blog](http://some-blog.io/blog)|[holiday](holiday)|[http://some-blog.io/holiday](http://some-blog.io/holiday)|


To understand why, you need to understand the [algorithm for transforming relative URIs into absolute URIs](https://tools.ietf.org/html/rfc3986#section-5).

The first step is to establish the base URI of a resource, in this case the base URI is the URI of the requested resource, i.e.: [http://some-blog.io](http://some-blog.io)

The next step is to merge the base URI with the relative URI, [RFC 3986](https://tools.ietf.org/html/rfc3986) describes this process, the relevant statement is:

> return a string consisting of the reference’s path component appended to all but the last segment of the base URI’s path (i.e., excluding any characters after the right-most “/” in the base URI path, or excluding the entire base URI path if it does not contain any “/” characters).

Therefore we must exclude any characters after the right-most “/” in [http://some-blog.io/blogs](http://some-blog.io/blogs), which gives: [http://some-blog.io/](http://some-blog.io/). Finally the relative URI ([holiday](holiday)) is appended to this URI, thus giving [http://some-blog.io/holiday](http://some-blog.io/holiday).

If a client attempts to retrieve [http://some-blog.io/holiday](http://some-blog.io/holiday) they will get a 404 Not Found error, because the resource doesn’t actually exist at that location.

#### Doing it right

|     Base URI    |   Relative URI  |Absolute URI   |
| ------------- |-------------| -----|
|[http://some-blog.io/blog/](http://some-blog.io/blog/)| [holiday](holiday) |[http://some-blog.io/blog/holiday](http://some-blog.io/blog/holiday)|

[Why trailing slashes on uris are important](https://cdivilly.wordpress.com/2014/03/11/why-trailing-slashes-on-uris-are-important/)