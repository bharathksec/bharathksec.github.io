---
title: My First Bounty A 100$ Stored Xss 
published: true
---

Hello Everyone.This is Bharath.In this blog iam gonna share about my first bounty that i got for a Stored xss.As it is my first blog expect some grammatical mistakes or typo.Let's start
Text can be **bold**, _italic_, ~~strikethrough~~ or `keyword`.

[Link to another page](another-page).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# [](#header-1)What is Stored Xss

You can learn about Stored Xss here
[portswigger](https://portswigger.net/web-security/cross-site-scripting/stored).


## [](#header-1)How did i find this

The target was public bug bounty program hosted in hackerone.It had so many funtion in main appliaction.I was testing each one of them when ever i see a input field i copy paste a xss payload in it.Nothing worked after some time of testing i found a chat box which enable you to chat with others

Started to test for xss.Then found that we can use markdown in chat like bold `**bold**`,italic `__italic__`,Codeblock ````codeblock````,Blockquote `>>Blockquote<<`.normally if we send a payload in chat it encode the payload to HTML entity.So tryed to inject a xss payload with the markdown like this
```js
**bold** <img src=x onerror=alert()>
```
The markdown for `**bold**`,`__italic__`,`>>Blockquote<<` did'nt work to my surprise codeblock worked.
```js
```codeblock``` <img src=x onerror=alert()>
```
I Just send this request and a xss payload poped.Then i tryed to inject alert cookie.
```js
```codeblock``` <img src=x onerror=alert(document.cookie)>
```
Worked.Out of curiosity i reported it.But don't do this try to escalate xss to ATO.

### [](#header-3)Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### [](#header-4)Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### [](#header-5)Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### [](#header-6)Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```