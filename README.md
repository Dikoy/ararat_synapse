# ararat_synapse
Ararat Synapse project fork (http://synapse.ararat.cz/). 
Checked out from (svn://svn.code.sf.net/p/synalist/code/trunk synalist-code).

# Synapse Library

## Project idea

The SYNAPSE library aims to create a complete library of classes and functions that would markedly simplify application programming of network communication using Winsock.

At first glance this effort might seem needless as there are many free components covering this area, However they mostly use asynchronous methods while SYNAPSE library operates in a synchronous method.

After having a look at 'competitive' libraries I must say all of them were created relatively early (for Delphi 1.0 and Win16). Thanks to cooperative multitasking, a synchronous access to Winsock was not possible. This is the reason why Microsoft added asynchronous mode to Winsock implementation.

Authors did not want to rewrite their libraries after WIN32 arrived and so their work still remains in asynchronous mode. Somewhere here is the root of Delphi programmers' myth that Winsock operates just asynchronously. However, synchronous mode is more natural in pre-emptive multitasking and multithreading environment. Synchronous mode (called 'blocking' in Winsock terminology) features acting thread waits until the needed operation terminates. Thus when we want to send data, the program exits function only after data is sent - or - if we want to receive data, the program exits the function only after the desired data is received.

Thus, much more crisp and simple programming is achieved. You especially feel it when trying to implement any Internet protocol, which is typically based on 'send-wait for reply' method. If you want to implement it in an asynchronous method, you would have to accept complicated event processing and synchronous mode simulation. Therefore a synchronous socket is simple and natural for the majority programming tasks.

The whole library is oriented on the WIN32 environment or Linux enviroment, so you will need Delphi 3.0 or higher and Kylix 1.0 or higher to use it. However some new ports for FreePascal are available too.

## Features

* Synapse is not a components suite, but only a group of classes and routines. No installation is needed! Just add the units to your uses clause.
* Works under Windows and under Linux.
* Can be compiled by Delphi, C++Builder, Kylix and FreePascal.
* Support for communicating by dynamically loaded Winsock or Libc in blocking mode (or any other compatible library).
* Supports TCP, UDP, ICMP and RAW protocols.
* Limited support for non-blocking communication mode.
* Can use IPv4 and IPv6 addresses.
* Native full SOCKS5 proxy support for TCP and UDP protocols.
* Native full SOCKS4/4a proxy support for TCP protocol.
* Support for TCP through HTTP proxy tunnel.
* Support for TCP with SSL/TLS by OpenSSL or SSLeay.
* Support for TCP with SSL/TLS by StreamSecII.
* Support for PING request by ICMP or ICMPv6.
* Support for ASN.1 coding and decoding.
* Support for DNS (TCP or UDP) with many non-standard records (includes zone transfers).
* Support for character code transcoding. Supported charsets are basic ISO codings (ISO-8859-x), windows codings (CP-125x), KOI8-R, CP-895 (Kamenicky), CP-852 (PC-Latin-2) and UNICODE (UCS-4, UCS-2, UTF-7 and UTF-8).
* Support for character replacing during character set transforms. (i.e. for removing diakritics, etc.)
* Support for coding and decoding MIME e-mail messages (includes character conversion of all supported charsets), includes inline MIME encoding.
* Support for SMTP and ESMTP protocol. SSL/TLS mode also supported.
* Support for HTTP protocol 0.9, 1.0 and 1.1. Can handle ANY HTTP method, KeepAlives, 100-status, Cookies and partial document downloading. HTTPS also supported.
* Support for SNMP protocol (include traps). Easy retrieval of SNMP tables, etc.
* Support for NTP and SNTP time protocols (include broadcast client).
* Support for POP3 protocol (classic and APOP login). SSL/TLS mode is also supported.
* Support for FTP protocol (support many firewalls including custom ones, upload and dowload resuming, transfer between two FTP servers). Implemented directory list parsing too. SSL/TLS support.
* Support for TFTP protocol (client and server).
* Support for LDAP protocol.
* Support BSD Syslog client for unified platform independent logging capability.
* Support for NNTP (Network News Transfer Protocol) including SSL/TLS support.
* Support for Telnet script client.
* Support for Base64 and Quoted-printable coding and decoding.
* Support for UUcode, XXcode and Yenc decoding.
* Support for calculating CRC16, CRC32, MD5 and HMAC-MD5.
* Support for autodetecting DNS servers or proxy settings.
* Wake-on-lan

