---
layout: post
title:  Throw statement with no expression
mathjax: false
comments: false
share: false
mathjax: false
tags:
- c_sharp

---

> You can also use the throw e syntax in a catch block to instantiate a new exception that you pass on to the caller. 
In this case, the stack trace of the original exception, which is available from the StackTrace property, is not preserved.

<!--more-->
``` c#
public void foo()
{
    try {
        // some code
    }
    catch (Exception e) 
    {
       throw e;
    }
}
```
vs
``` c#
public void foo()
{
    try {
        // some code
    }
    catch (Exception) 
    {
       throw;
    }
}
```
[throw (C# Reference)](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/throw)
