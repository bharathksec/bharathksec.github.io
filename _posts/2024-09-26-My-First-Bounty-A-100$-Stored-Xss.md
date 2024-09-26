---
title: My First Bounty A 100$ Stored Xss 
published: true
---

Hello Everyone.This is Bharath.In this blog iam gonna share about my first bounty that i got for a Stored xss.As it is my first blog expect some grammatical mistakes or typo.Let's start

# [](#header-1)What is Stored Xss

You can learn about Stored Xss here
[portswigger](https://portswigger.net/web-security/cross-site-scripting/stored).


# [](#header-1)How did i find this

The target was public bug bounty program hosted in hackerone.It had so many funtion in main appliaction.I was testing each one of them when ever i see a input field i copy paste a xss payload in it.Nothing worked after some time of testing i found a chat box which enable you to chat with others

Started to test for xss.Then found that we can use markdown in chat like bold `**bold**`,italic `__italic__`,Codeblock ````codeblock````,Blockquote `>>Blockquote<<`.normally if we send a payload in chat it encode the payload to HTML entity.So tryed to inject a xss payload with the markdown like this
```js
**bold** <img src=x onerror=alert()>
```
The markdown for `**bold**`,`__italic__`,`>>Blockquote<<` did'nt work to my surprise codeblock worked.
```js
```codeblock``` <img src=x onerror=alert()>
```
I Just pasted this xss payload in chat clicked enter and a xss payload poped.I was so surprised to see that Then i tryed to inject alert cookie.
```js
```codeblock``` <img src=x onerror=alert(document.cookie)>
```
Worked.Out of curiosity i reported it.But don't do this try to escalate xss to ATO.

# [](#header-1)
