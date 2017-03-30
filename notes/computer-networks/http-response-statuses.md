## HTTP Response Statuses

Official Docs: https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html

W3Schools: https://www.w3schools.com/tags/ref_httpmessages.asp

### Examples

### 301

From the command line:

```` sh
curl google.com
````

=>

```` html
<HTML>
  <HEAD>
    <meta http-equiv="content-type" content="text/html;charset=utf-8">
    <TITLE>301 Moved</TITLE>
  </HEAD>
  <BODY>
      <H1>301 Moved</H1>
      The document has moved <A HREF="http://www.google.com/">here</A>.
  </BODY>
</HTML>
````
