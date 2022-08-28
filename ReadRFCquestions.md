# Read The RFC 

- RFCs or **Request for Comments**, is the way that the internet develops standards. Read this to learn more: [Lifewire: What is an RFC](https://www.lifewire.com/what-is-internet-request-for-comments-rfc-4092366)


1. Is this an official RFC? What RFC did it update?
  
  - This is official [RFC 7231 HTTP/1.](https://www.rfc-editor.org/rfc/rfc7231.txt) which updates [RFC 2817](https://www.rfc-editor.org/rfc/rfc2817) and is dated June 2022.  


2. What does this RFC give guidance on how to do

  - This RFC gives guidance on HTTP/1.1 Semantics and Content. It explains HTTP, the syntax, and error handeling.  

3. What is a GET request and what does it look like?

  - A GET request method requests transfer of a current selected representation for the target resource. GET is the primary mechanism of information retrieval and the focus of almost all performance optimizations. Hence when people speak of retrieving some identifiable information via HTTP, they are generally reffering to making a GET request.

4. What is a User-Agent?

  - The "User-Agent" is a  header field containing information about the user agent originating the request, which is often used by servers to help identify the scope of reported interoperability problems, to work around or tailor responses to avoid particular user agent limitations, and for analytics regarding browser or operating system use. A user agent **SHOULD** send a User-Agent field in each request unless specifically configured not to do so.

  `User-Agent = product *( RWS ( product / comment ) )`
