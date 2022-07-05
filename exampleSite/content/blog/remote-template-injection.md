+++
categories = ["Red Teaming", "Microsoft Office"]
date = 2022-06-29T15:00:00Z
description = "this is meta description"
image = "images/post/remote.png"
tags = ["Remote Template Injection"]
title = "Remote Template Injection "
type = "post"

+++
##### Remote Template Injection Explained

Injecting malicious macros into Microsoft Word documents is by no means a new and novel attack vector. It's been used to death, literally. Microsoft will disable all macros by default **in?**

A red team specialist (or malicious actor) will write and inject some malicious VBA code in the macro section of an office document that will execute using **AUTO_OPEN** when the document is loaded. The document itself usually contains some content that is related to the attack or phishing scenario. For example, sending a resume to a human resources department. The majority of good AV and EDR solutions will detect this attack today and block execution of the macro payload.

Now, imagine having a document that doesn't include malicious code. A completely safe, friendly, innocent and benign .docx file. Except, that the document contains a link to a malicious remote template document that will load once the document is opened. This attack vector is known as remote template injection. Malicious code is stored remotely and and loaded as a remote template, without even touching the disk.

##### Attack Demonstration

This demonstration is for educational purposes only. Don't be an idiot. Use your hacking skills to make the world a better and safer place.

In the following demo, I will use C#, TrustedSec's Unicorn and PowerShell to create a .docx file with a link to a malicious remote template that will execute once the document is open. In this demo, I am using Cobalt Strike but you can use any C2 of your choosing.

##### 1: Generate the Payload

![image](/uploads/rti_1.png "Generate Payload")

##### Link

[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a reference-style link](https://www.mozilla.org)

[I'm a relative reference to a repository file](../blob/master/LICENSE)

[You can use numbers for reference-style link definitions](http://slashdot.org)

Or leave it empty and use the [link text itself](http://www.reddit.com).

URLs and URLs in angle brackets will automatically get turned into links.
http://www.example.com or [http://www.example.com](http://www.example.com) and sometimes
example.com (but not on Github, for example).

Some text to show that the reference links can follow later.

<hr>

##### Paragraph

Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam nihil enim maxime corporis cumque totam aliquid nam sint inventore optio modi neque laborum officiis necessitatibus, facilis placeat pariatur! Voluptatem, sed harum pariatur adipisci voluptates voluptatum cumque, porro sint minima similique magni perferendis fuga! Optio vel ipsum excepturi tempore reiciendis id quidem? Vel in, doloribus debitis nesciunt fugit sequi magnam accusantium modi neque quis, vitae velit, pariatur harum autem a! Velit impedit atque maiores animi possimus asperiores natus repellendus excepturi sint architecto eligendi non, omnis nihil. Facilis, doloremque illum. Fugit optio laborum minus debitis natus illo perspiciatis corporis voluptatum rerum laboriosam.

* 

<hr>

##### Code and Syntax Highlighting

Inline `code` has `back-ticks around` it.

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

```python
s = "Python syntax highlighting"
print s
```

    No language indicated, so no syntax highlighting. 
    But let's throw in a <b>tag</b>.

<hr>

##### Blockquote

> This is a blockquote example.

<hr>

##### Inline HTML

You can also use raw HTML in your Markdown, and it'll mostly work pretty well.

<dl>
<dt>Definition list</dt>
<dd>Is something people use sometimes.</dd>

<dt>Markdown in HTML</dt>
<dd>Does _not_ work **very** well. Use HTML <em>tags</em>.</dd>
</dl>

<hr>

##### Tables

Colons can be used to align columns.

| Tables | Are | Cool |
| --- | :---: | ---: |
| col 3 is | right-aligned | $1600 |
| col 2 is | centered | $12 |
| zebra stripes | are neat | $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the
raw Markdown line up prettily. You can also use inline Markdown.

| Markdown | Less | Pretty |
| --- | --- | --- |
| Still | renders | nicely |
| 1 | 2 | 3 |

<hr>

##### Image

![image](../../images/post/post-1.jpg)

<hr>