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

<br />

Note: The filenames contain information about platform and compatiblity.
      You may need to change to the Github file listing view to easily
      see the full filename.

<br />

Particular details to keep in mind
--
* [Android supports TLS 1.0 since 2.3][android-tls]
* Windows XP does not support AES cipher suites
* Windows Server 2003 does not support AES natively, but support was added in [KB948963][ms-2003-aes]
* Windows Server 2003 and XP with IE 6 support TLS 1.0 after a configuration change.
* Windows Server 2003 and XP with IE 8 support TLS 1.0 by default.
* Settings provided in this repository impact how the Windows operating sytem handles SSL and TLS. This affects all applications that do not use their own libraries for SSL and TLS.

Terminology usage in this repository
--
* 'Max Compability' indicates TLS protocol support for SSL 3.0 and TLS 1.0, 1.1, 1.2
* 'High Security' indicates cipher suite settings that break Internet Explorer 6 era code by removal of RC4 and 3DES.

General Process
--
1. Select a Cipher_Suites file matching your desired level of compatibility and security. Cipher suite selection dictate:
  1. Key agreement/key exchange protocols such as RSA, DSA, DH, ECHE, ECDHE
  2. Symetric encryption algorithms such as AES, RC4, 3DES
  3. Message authentication algorithms such as MD5, SHA1, SHA256, SHA384
  
2. Select an SChannel_config matching your level level of compatibility and security. SChannel settings dictate:
  1. SSL / TLS protocols supported such as SSL 2.0, 3.0, and TLS 1.0, 1.1, 1.2
  2. Enabling or disabling certain ciphers entirely such as NULL, DES, RC2, RC4 

3. Download these to your server.

4. Review all the settings and make sure you understand them! ** NO WARRANTY **

5. Double click to install each, review and accept each warning message.

6. Restart the server.

7. Test with the [Qualys' SSL Labs site][ssllabs] - https://www.ssllabs.com/ssltest/analyze.html

8. Test with representative clients.

References
--
* [SSL / TLS Browser compatibility chart - Wikipedia][wiki-tls-compat]
* [Microsoft patch to add limited AES support to Windows Server 2003 - KB948963][ms-2003-aes]
* [Cipher Suites in Microsoft Schannel][ms-schannel]
* [How to restrict the use of certain cryptographic algorithms and protocols in Schannel.dll][ms-restrict]



[ssllabs]: https://www.ssllabs.com/ssltest/analyze.html
[ivan-blog]: http://blog.ivanristic.com/
[ivan-book]: https://www.feistyduck.com/books/bulletproof-ssl-and-tls/
[adam-blog]: https://www.imperialviolet.org/
[twitter-link]: https://twitter.com/TomSellers
[wiki-tls-compat]: http://en.wikipedia.org/wiki/Transport_Layer_Security#Web_browsers
[ms-2003-aes]: http://support.microsoft.com/kb/948963
[ms-schannel]: http://msdn.microsoft.com/en-us/library/windows/desktop/aa374757(v=vs.85).aspx
[ms-restrict]: http://support.microsoft.com/kb/245030
[android-tls]: https://developer.android.com/training/articles/security-ssl.html
