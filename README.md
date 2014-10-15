Microsoft Windows SSL / TLS Configuration
==

The intent of this repository is to provide working configuration settings 
that can be used to implement SSL and TLS with various levels of 
compatibility and security.

If the information and settings in this repository are correct then Ivan 
Ristic's [blog][ivan-blog] and book [Bulletproof SSL and TLS][ivan-book] or 
[Adam Langley's blog][adam-blog] are likely to thank.

If anything in this repository is incorrect then it is definitely my fault.
Corrections and suggestions are greatly appreciated via GitHub or Twitter 
at [@TomSellers][twitter-link]


General Process
--
1. Select a Cipher_Suites file matching your desired level of compatibility and security.
2. Select an SChannel_config matching your level level of compatibility and security.
3. Download these to your server.
4. Double click to install each, review and accept each warning message.
5. Restart the server.
6. Test with the [Qualys' SSL Labs site][ssllabs] - https://www.ssllabs.com/ssltest/analyze.html
7. Test with representative clients.

References
* [SSL / TLS Browser compatibility chart - Wikipedia][wiki-tls-compat]
* [Microsoft patch to add limited AES support to Windows Server 2003 - KB948963][ms-2003-aes]
* [Cipher Suites in Microsoft Schannel][ms-schannel]



[ssllabs]: https://www.ssllabs.com/ssltest/analyze.html
[ivan-blog]: http://blog.ivanristic.com/
[ivan-book]: https://www.feistyduck.com/books/bulletproof-ssl-and-tls/
[adam-blog]: https://www.imperialviolet.org/
[twitter-link]: https://twitter.com/TomSellers
[wiki-tls-compat]: http://en.wikipedia.org/wiki/Transport_Layer_Security#Web_browsers
[ms-2003-aes]: http://support.microsoft.com/kb/948963
[ms-schannel]: http://msdn.microsoft.com/en-us/library/windows/desktop/aa374757(v=vs.85).aspx
