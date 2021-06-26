Title: Apache HTTP Server 2.2 vulnerabilities

<h1>Apache HTTP Server 2.2 vulnerabilities</h1>
<p>This page lists all security vulnerabilities fixed in released versions of Apache HTTP Server 2.2. Each vulnerability is given a security <a href="/security/impact_levels.html">impact rating</a> by the Apache security team - please note that this rating may well vary from platform to platform.  We also list the versions the flaw is known to affect, and where a flaw has not been verified list the version with a question mark.</p>
<p>Please note that if a vulnerability is shown below as being fixed in a "-dev" release then this means that a fix has been applied to the development source tree and will be part of an upcoming full release.</p>
<p>Please send comments or corrections for these vulnerabilities to the <a href="/security_report.html">Security Team</a>.</p> <br/>
<p><h3>Apache httpd 2.2 is End-of-Life since December 2017 and should not be used.   This page only lists security issues that occurred before the End-of-Life.  Subsequent issues may have affected 2.2 but will not be investigated or listed here.  Users are advised to upgrade to the currently supported released version to address known issues.</h3></p><br/>

<h1 id="2.2.35-never">Fixed in Apache HTTP Server 2.2.35-never</h1><dl>

<dt><h3 id="CVE-2017-9798">low: <name name="CVE-2017-9798">Use-after-free when using &lt;Limit &gt; with an unrecognized method in .htaccess ("OptionsBleed")</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-9798">CVE-2017-9798</a>)</h3></dt>
<dd><p>When an unrecognized HTTP Method is given in an &lt;Limit {method}&gt; directive in an .htaccess file, and that .htaccess file is processed by the corresponding request, the global methods table is corrupted in the current worker process, resulting in erratic behaviour. This behavior may be avoided by listing all unusual HTTP Methods in a global httpd.conf RegisterHttpMethod directive in httpd release 2.4.25 and later. To permit other .htaccess directives while denying the &lt;Limit &gt; directive, see the AllowOverrideList directive. Source code patch (2.4) is at; CVE-2017-9798-patch-2.4.patch Source code patch (2.2) is at; CVE-2017-9798-patch-2.2.patch Note 2.2 is end-of-life, no further release with this fix is planned. Users are encouraged to migrate to 2.4.28 or later for this and other fixes.</p>
<p>Acknowledgements: We would like to thank Hanno Böck for reporting this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2017-07-12</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2017-09-18</td></tr>
<tr><td class="cve-header">Update 2.4.28 released</td><td class="cve-value">2017-10-05</td></tr>
<tr><td class="cve-header">Update 2.2.35-never released</td><td class="cve-value">--</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.27, 2.4.26, 2.4.25, 2.4.23, 2.4.20, 2.4.18, 2.4.17, 2.4.16, 2.4.12, 2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.34, 2.2.32, 2.2.31, 2.2.29, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.34">Fixed in Apache HTTP Server 2.2.34</h1><dl>

<dt><h3 id="CVE-2017-3167">important: <name name="CVE-2017-3167">ap_get_basic_auth_pw() Authentication Bypass</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-3167">CVE-2017-3167</a>)</h3></dt>
<dd><p>Use of the ap_get_basic_auth_pw() by third-party modules outside of the authentication phase may lead to authentication requirements being bypassed. Third-party module writers SHOULD use ap_get_basic_auth_components(), available in 2.2.34 and 2.4.26, instead of ap_get_basic_auth_pw(). Modules which call the legacy ap_get_basic_auth_pw() during the authentication phase MUST either immediately authenticate the user after the call, or else stop the request immediately with an error response, to avoid incorrectly authenticating the current request.</p>
<p>Acknowledgements: We would like to thank Emmanuel Dreyfus for reporting this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2017-02-06</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2017-06-19</td></tr>
<tr><td class="cve-header">Update 2.4.26 released</td><td class="cve-value">2017-06-19</td></tr>
<tr><td class="cve-header">Update 2.2.34 released</td><td class="cve-value">2017-07-11</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.25, 2.4.23, 2.4.20, 2.4.18, 2.4.17, 2.4.16, 2.4.12, 2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.32, 2.2.31, 2.2.29, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2017-3169">important: <name name="CVE-2017-3169">mod_ssl Null Pointer Dereference</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-3169">CVE-2017-3169</a>)</h3></dt>
<dd><p>mod_ssl may dereference a NULL pointer when third-party modules call ap_hook_process_connection() during an HTTP request to an HTTPS port.</p>
<p>Acknowledgements: We would like to thank Vasileios Panopoulos and AdNovum Informatik AG for reporting this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2016-12-05</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2017-06-19</td></tr>
<tr><td class="cve-header">Update 2.4.26 released</td><td class="cve-value">2017-06-19</td></tr>
<tr><td class="cve-header">Update 2.2.34 released</td><td class="cve-value">2017-07-11</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.25, 2.4.23, 2.4.20, 2.4.18, 2.4.17, 2.4.16, 2.4.12, 2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.32, 2.2.31, 2.2.29, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2017-7668">important: <name name="CVE-2017-7668">ap_find_token() Buffer Overread</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-7668">CVE-2017-7668</a>)</h3></dt>
<dd><p>The HTTP strict parsing changes added in 2.2.32 and 2.4.24 introduced a bug in token list parsing, which allows ap_find_token() to search past the end of its input string. By maliciously crafting a sequence of request headers, an attacker may be able to cause a segmentation fault, or to force ap_find_token() to return an incorrect value.</p>
<p>Acknowledgements: We would like to thank Javier Jiménez (javijmor@gmail.com) for reporting this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2017-05-06</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2017-06-19</td></tr>
<tr><td class="cve-header">Update 2.4.26 released</td><td class="cve-value">2017-06-19</td></tr>
<tr><td class="cve-header">Update 2.2.34 released</td><td class="cve-value">2017-07-11</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.25, 2.2.32</td></tr>
</table></dd>
<dt><h3 id="CVE-2017-7679">important: <name name="CVE-2017-7679">mod_mime Buffer Overread</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-7679">CVE-2017-7679</a>)</h3></dt>
<dd><p>mod_mime can read one byte past the end of a buffer when sending a malicious Content-Type response header.</p>
<p>Acknowledgements: We would like to thank ChenQin and Hanno Böck for reporting this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2015-11-15</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2017-06-19</td></tr>
<tr><td class="cve-header">Update 2.4.26 released</td><td class="cve-value">2017-06-19</td></tr>
<tr><td class="cve-header">Update 2.2.34 released</td><td class="cve-value">2017-07-11</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.25, 2.4.23, 2.4.20, 2.4.18, 2.4.17, 2.4.16, 2.4.12, 2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.32, 2.2.31, 2.2.29, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2017-9788">important: <name name="CVE-2017-9788">Uninitialized memory reflection in mod_auth_digest</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-9788">CVE-2017-9788</a>)</h3></dt>
<dd><p>The value placeholder in [Proxy-]Authorization headers of type 'Digest' was not initialized or reset before or between successive key=value assignments. by mod_auth_digest. Providing an initial key with no '=' assignment could reflect the stale value of uninitialized pool memory used by the prior request, leading to leakage of potentially confidential information, and a segfault.</p>
<p>Acknowledgements: We would like to thank Robert Święcki for reporting this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2017-06-28</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2017-07-11</td></tr>
<tr><td class="cve-header">Update 2.4.27 released</td><td class="cve-value">2017-07-11</td></tr>
<tr><td class="cve-header">Update 2.2.34 released</td><td class="cve-value">2017-07-11</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.26, 2.4.25, 2.4.23, 2.4.20, 2.4.18, 2.4.17, 2.4.16, 2.4.12, 2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.32, 2.2.31, 2.2.29, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.32">Fixed in Apache HTTP Server 2.2.32</h1><dl>

<dt><h3 id="CVE-2016-4975">moderate: <name name="CVE-2016-4975">mod_userdir CRLF injection</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-4975">CVE-2016-4975</a>)</h3></dt>
<dd><p>Possible CRLF injection allowing HTTP response splitting attacks for sites which use mod_userdir. This issue was mitigated by changes made in 2.4.25 and 2.2.32 which prohibit CR or LF injection into the "Location" or other outbound header key or value.</p>
<p>Acknowledgements: The issue was discovered by Sergey Bobrov</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2016-07-24</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2018-08-14</td></tr>
<tr><td class="cve-header">Update 2.4.25 released</td><td class="cve-value">2016-12-20</td></tr>
<tr><td class="cve-header">Update 2.2.32 released</td><td class="cve-value">2017-01-13</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.23, 2.4.20, 2.4.18, 2.4.17, 2.4.16, 2.4.12, 2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.31, 2.2.29, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2016-5387">n/a: <name name="CVE-2016-5387">HTTP_PROXY environment variable "httpoxy" mitigation</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-5387">CVE-2016-5387</a>)</h3></dt>
<dd><p>HTTP_PROXY is a well-defined environment variable in a CGI process, which collided with a number of libraries which failed to avoid colliding with this CGI namespace. A mitigation is provided for the httpd CGI environment to avoid populating the "HTTP_PROXY" variable from a "Proxy:" header, which has never been registered by IANA. This workaround and patch are documented in the ASF Advisory at asf-httpoxy-response.txt and incorporated in the 2.4.25 and 2.2.32 releases. Note: This is not assigned an httpd severity, as it is a defect in other software which overloaded well-established CGI environment variables, and does not reflect an error in HTTP server software.</p>
<p>Acknowledgements: We would like to thank Dominic Scheirlinck and Scott Geary of Vend for reporting and proposing a fix for this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2016-07-02</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2016-07-18</td></tr>
<tr><td class="cve-header">Update 2.4.25 released</td><td class="cve-value">2016-12-20</td></tr>
<tr><td class="cve-header">Update 2.2.32 released</td><td class="cve-value">2016-07-18</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.23, 2.4.20, 2.4.18, 2.4.17, 2.4.16, 2.4.12, 2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.31, 2.2.29, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2016-8743">important: <name name="CVE-2016-8743">Apache HTTP Request Parsing Whitespace Defects</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-8743">CVE-2016-8743</a>)</h3></dt>
<dd><p>Apache HTTP Server, prior to release 2.4.25 (and 2.2.32), accepted a broad pattern of unusual whitespace patterns from the user-agent, including bare CR, FF, VTAB in parsing the request line and request header lines, as well as HTAB in parsing the request line. Any bare CR present in request lines was treated as whitespace and remained in the request field member "the_request", while a bare CR in the request header field name would be honored as whitespace, and a bare CR in the request header field value was retained the input headers array. Implied additional whitespace was accepted in the request line and prior to the ':' delimiter of any request header lines.</p><p>RFC7230 Section 3.5 calls out some of these whitespace exceptions, and section 3.2.3 eliminated and clarified the role of implied whitespace in the grammer of this specification. Section 3.1.1 requires exactly one single SP between the method and request-target, and between the request-target and HTTP-version, followed immediately by a CRLF sequence. None of these fields permit any (unencoded) CTL character whatsoever. Section 3.2.4 explicitly disallowed any whitespace from the request header field prior to the ':' character, while Section 3.2 disallows all CTL characters in the request header line other than the HTAB character as whitespace.</p><p>These defects represent a security concern when httpd is participating in any chain of proxies or interacting with back-end application servers, either through mod_proxy or using conventional CGI mechanisms. In each case where one agent accepts such CTL characters and does not treat them as whitespace, there is the possiblity in a proxy chain of generating two responses from a server behind the uncautious proxy agent. In a sequence of two requests, this results in request A to the first proxy being interpreted as requests A + A' by the backend server, and if requests A and B were submitted to the first proxy in a keepalive connection, the proxy may interpret response A' as the response to request B, polluting the cache or potentially serving the A' content to a different downstream user-agent.</p><p>These defects are addressed with the release of Apache HTTP Server 2.4.25 and coordinated by a new directive; HttpProtocolOptions Strict which is the default behavior of 2.4.25 and later.</p><p>By toggling from 'Strict' behavior to 'Unsafe' behavior, some of the restrictions may be relaxed to allow some invalid HTTP/1.1 clients to communicate with the server, but this will reintroduce the possibility of the problems described in this assessment. Note that relaxing the behavior to 'Unsafe' will still not permit raw CTLs other than HTAB (where permitted), but will allow other RFC requirements to not be enforced, such as exactly two SP characters in the request line.</p>
<p>Acknowledgements: We would like to thank David Dennerline at IBM Security's X-Force Researchers as well as Régis Leroy for each reporting this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2016-02-10</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2016-12-20</td></tr>
<tr><td class="cve-header">Update 2.4.25 released</td><td class="cve-value">2016-12-20</td></tr>
<tr><td class="cve-header">Update 2.2.32 released</td><td class="cve-value">2017-01-13</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.23, 2.4.20, 2.4.18, 2.4.17, 2.4.16, 2.4.12, 2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.31, 2.2.29, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.31">Fixed in Apache HTTP Server 2.2.31</h1><dl>

<dt><h3 id="CVE-2015-3183">low: <name name="CVE-2015-3183">HTTP request smuggling attack against chunked request parser</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-3183">CVE-2015-3183</a>)</h3></dt>
<dd><p>An HTTP request smuggling attack was possible due to a bug in parsing of chunked requests. A malicious client could force the server to misinterpret the request length, allowing cache poisoning or credential hijacking if an intermediary proxy is in use.</p>
<p>Acknowledgements: This issue was reported by Régis Leroy.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2015-04-04</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2015-06-09</td></tr>
<tr><td class="cve-header">Update 2.4.16 released</td><td class="cve-value">2015-07-15</td></tr>
<tr><td class="cve-header">Update 2.2.31 released</td><td class="cve-value">2015-07-16</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.12, 2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.29, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.29">Fixed in Apache HTTP Server 2.2.29</h1><dl>

<dt><h3 id="CVE-2013-5704">low: <name name="CVE-2013-5704">HTTP Trailers processing bypass</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2013-5704">CVE-2013-5704</a>)</h3></dt>
<dd><p>HTTP trailers could be used to replace HTTP headers late during request processing, potentially undoing or otherwise confusing modules that examined or modified request headers earlier. This fix adds the "MergeTrailers" directive to restore legacy behavior.</p>
<p>Acknowledgements: This issue was reported by Martin Holst Swende.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2013-09-06</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2013-10-19</td></tr>
<tr><td class="cve-header">Update 2.4.12 released</td><td class="cve-value">2015-01-30</td></tr>
<tr><td class="cve-header">Update 2.2.29 released</td><td class="cve-value">2014-09-03</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.10, 2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2014-0118">moderate: <name name="CVE-2014-0118">mod_deflate denial of service</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-0118">CVE-2014-0118</a>)</h3></dt>
<dd><p>A resource consumption flaw was found in mod_deflate. If request body decompression was configured (using the "DEFLATE" input filter), a remote attacker could cause the server to consume significant memory and/or CPU resources. The use of request body decompression is not a common configuration.</p>
<p>Acknowledgements: This issue was reported by Giancarlo Pellegrino and Davide Balzarotti</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2014-02-19</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2014-07-14</td></tr>
<tr><td class="cve-header">Update 2.4.10 released</td><td class="cve-value">2014-07-15</td></tr>
<tr><td class="cve-header">Update 2.2.29 released</td><td class="cve-value">2014-09-03</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2014-0226">moderate: <name name="CVE-2014-0226">mod_status buffer overflow</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-0226">CVE-2014-0226</a>)</h3></dt>
<dd><p>A race condition was found in mod_status. An attacker able to access a public server status page on a server using a threaded MPM could send a carefully crafted request which could lead to a heap buffer overflow. Note that it is not a default or recommended configuration to have a public accessible server status page.</p>
<p>Acknowledgements: This issue was reported by Marek Kroemeke, AKAT-1 and 22733db72ab3ed94b5f8a1ffcde850251fe6f466 via HP ZDI</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2014-05-30</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2014-07-14</td></tr>
<tr><td class="cve-header">Update 2.4.10 released</td><td class="cve-value">2014-07-15</td></tr>
<tr><td class="cve-header">Update 2.2.29 released</td><td class="cve-value">2014-09-03</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2014-0231">important: <name name="CVE-2014-0231">mod_cgid denial of service</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-0231">CVE-2014-0231</a>)</h3></dt>
<dd><p>A flaw was found in mod_cgid. If a server using mod_cgid hosted CGI scripts which did not consume standard input, a remote attacker could cause child processes to hang indefinitely, leading to denial of service.</p>
<p>Acknowledgements: This issue was reported by Rainer Jung of the ASF</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2014-06-16</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2014-07-14</td></tr>
<tr><td class="cve-header">Update 2.4.10 released</td><td class="cve-value">2014-07-15</td></tr>
<tr><td class="cve-header">Update 2.2.29 released</td><td class="cve-value">2014-09-03</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.9, 2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.27, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.27">Fixed in Apache HTTP Server 2.2.27</h1><dl>

<dt><h3 id="CVE-2013-6438">moderate: <name name="CVE-2013-6438">mod_dav crash</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2013-6438">CVE-2013-6438</a>)</h3></dt>
<dd><p>XML parsing code in mod_dav incorrectly calculates the end of the string when removing leading spaces and places a NUL character outside the buffer, causing random crashes. This XML parsing code is only used with DAV provider modules that support DeltaV, of which the only publicly released provider is mod_dav_svn.</p>
<p>Acknowledgements: This issue was reported by Ning Zhang &amp; Amin Tora of Neustar</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2013-12-10</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2014-03-17</td></tr>
<tr><td class="cve-header">Update 2.4.9 released</td><td class="cve-value">2014-03-17</td></tr>
<tr><td class="cve-header">Update 2.2.27 released</td><td class="cve-value">2014-03-26</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2014-0098">low: <name name="CVE-2014-0098">mod_log_config crash</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-0098">CVE-2014-0098</a>)</h3></dt>
<dd><p>A flaw was found in mod_log_config. A remote attacker could send a specific truncated cookie causing a crash. This crash would only be a denial of service if using a threaded MPM.</p>
<p>Acknowledgements: This issue was reported by Rainer M Canavan</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2014-02-25</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2014-03-17</td></tr>
<tr><td class="cve-header">Update 2.4.9 released</td><td class="cve-value">2014-03-17</td></tr>
<tr><td class="cve-header">Update 2.2.27 released</td><td class="cve-value">2014-03-26</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.7, 2.4.6, 2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.26, 2.2.25, 2.2.24, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.25">Fixed in Apache HTTP Server 2.2.25</h1><dl>

<dt><h3 id="CVE-2013-1862">low: <name name="CVE-2013-1862">mod_rewrite log escape filtering</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2013-1862">CVE-2013-1862</a>)</h3></dt>
<dd><p>mod_rewrite does not filter terminal escape sequences from logs, which could make it easier for attackers to insert those sequences into terminal emulators containing vulnerabilities related to escape sequences.</p>
<p>Acknowledgements: This issue was reported by Ramiro Molina</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2013-03-13</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2013-04-19</td></tr>
<tr><td class="cve-header">Update 2.2.25 released</td><td class="cve-value">2013-07-22</td></tr>
<tr><td class="cve-header">Update 2.0.65 released</td><td class="cve-value">2013-07-22</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.64, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2013-1896">moderate: <name name="CVE-2013-1896">mod_dav crash</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2013-1896">CVE-2013-1896</a>)</h3></dt>
<dd><p>Sending a MERGE request against a URI handled by mod_dav_svn with the source href (sent as part of the request body as XML) pointing to a URI that is not configured for DAV will trigger a segfault.</p>
<p>Acknowledgements: This issue was reported by Ben Reser</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2013-03-07</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2013-05-23</td></tr>
<tr><td class="cve-header">Update 2.4.6 released</td><td class="cve-value">2013-07-22</td></tr>
<tr><td class="cve-header">Update 2.2.25 released</td><td class="cve-value">2013-07-22</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.4, 2.4.3, 2.4.2, 2.4.1, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.24">Fixed in Apache HTTP Server 2.2.24</h1><dl>

<dt><h3 id="CVE-2012-3499">low: <name name="CVE-2012-3499">XSS due to unescaped hostnames</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-3499">CVE-2012-3499</a>)</h3></dt>
<dd><p>Various XSS flaws due to unescaped hostnames and URIs HTML output in mod_info, mod_status, mod_imagemap, mod_ldap, and mod_proxy_ftp.</p>
<p>Acknowledgements: This issue was reported by Niels Heinen of Google</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2012-07-11</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2013-02-18</td></tr>
<tr><td class="cve-header">Update 2.4.4 released</td><td class="cve-value">2013-02-25</td></tr>
<tr><td class="cve-header">Update 2.2.24 released</td><td class="cve-value">2013-02-25</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.3, 2.4.2, 2.4.1, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2012-4558">moderate: <name name="CVE-2012-4558">XSS in mod_proxy_balancer</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-4558">CVE-2012-4558</a>)</h3></dt>
<dd><p>A XSS flaw affected the mod_proxy_balancer manager interface.</p>
<p>Acknowledgements: This issue was reported by Niels Heinen of Google</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2012-10-07</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2013-02-18</td></tr>
<tr><td class="cve-header">Update 2.4.4 released</td><td class="cve-value">2013-02-25</td></tr>
<tr><td class="cve-header">Update 2.2.24 released</td><td class="cve-value">2013-02-25</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.3, 2.4.2, 2.4.1, 2.2.23, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.23">Fixed in Apache HTTP Server 2.2.23</h1><dl>

<dt><h3 id="CVE-2012-0883">low: <name name="CVE-2012-0883">insecure LD_LIBRARY_PATH handling</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-0883">CVE-2012-0883</a>)</h3></dt>
<dd><p>Insecure handling of LD_LIBRARY_PATH was found that could lead to the current working directory to be searched for DSOs. This could allow a local user to execute code as root if an administrator runs apachectl from an untrusted directory.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2012-02-14</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2012-03-02</td></tr>
<tr><td class="cve-header">Update 2.4.2 released</td><td class="cve-value">2012-04-17</td></tr>
<tr><td class="cve-header">Update 2.2.23 released</td><td class="cve-value">2012-09-13</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.1, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2012-2687">low: <name name="CVE-2012-2687">XSS in mod_negotiation when untrusted uploads are supported</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-2687">CVE-2012-2687</a>)</h3></dt>
<dd><p>Possible XSS for sites which use mod_negotiation and allow untrusted uploads to locations which have MultiViews enabled. Note: This issue is also known as CVE-2008-0455.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2012-05-31</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2012-06-13</td></tr>
<tr><td class="cve-header">Update 2.2.23 released</td><td class="cve-value">2012-09-13</td></tr>
<tr><td class="cve-header">Update 2.4.3 released</td><td class="cve-value">2012-08-21</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.4.2, 2.4.1, 2.2.22, 2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.22">Fixed in Apache HTTP Server 2.2.22</h1><dl>

<dt><h3 id="CVE-2011-3368">moderate: <name name="CVE-2011-3368">mod_proxy reverse proxy exposure</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-3368">CVE-2011-3368</a>)</h3></dt>
<dd><p>An exposure was found when using mod_proxy in reverse proxy mode. In certain configurations using RewriteRule with proxy flag or ProxyPassMatch, a remote attacker could cause the reverse proxy to connect to an arbitrary server, possibly disclosing sensitive information from internal web servers not directly accessible to attacker. No update of 1.3 will be released.</p><p>Patches will be published to https://archive.apache.org/dist/httpd/patches/apply_to_1.3.42/</p>
<p>Acknowledgements: This issue was reported by Context Information Security Ltd</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2011-09-16</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2011-10-05</td></tr>
<tr><td class="cve-header">Update 2.2.22 released</td><td class="cve-value">2012-01-31</td></tr>
<tr><td class="cve-header">Update 2.0.65 released</td><td class="cve-value">2013-07-22</td></tr>
<tr><td class="cve-header">Update 1.3-never released</td><td class="cve-value">--</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.64, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.42, 1.3.41, 1.3.39, 1.3.37, 1.3.36, 1.3.35, 1.3.34, 1.3.33, 1.3.32, 1.3.31, 1.3.29, 1.3.28, 1.3.27, 1.3.26, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2</td></tr>
</table></dd>
<dt><h3 id="CVE-2011-3607">low: <name name="CVE-2011-3607">mod_setenvif .htaccess privilege escalation</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-3607">CVE-2011-3607</a>)</h3></dt>
<dd><p>An integer overflow flaw was found which, when the mod_setenvif module is enabled, could allow local users to gain privileges via a .htaccess file.</p>
<p>Acknowledgements: This issue was reported by halfdog</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2011-10-04</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2011-11-02</td></tr>
<tr><td class="cve-header">Update 2.2.22 released</td><td class="cve-value">2012-01-31</td></tr>
<tr><td class="cve-header">Update 2.0.65 released</td><td class="cve-value">2013-07-22</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.64, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2011-4317">moderate: <name name="CVE-2011-4317">mod_proxy reverse proxy exposure</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-4317">CVE-2011-4317</a>)</h3></dt>
<dd><p>An additional exposure was found when using mod_proxy in reverse proxy mode. In certain configurations using RewriteRule with proxy flag or ProxyPassMatch, a remote attacker could cause the reverse proxy to connect to an arbitrary server, possibly disclosing sensitive information from internal web servers not directly accessible to attacker.</p>
<p>Acknowledgements: This issue was reported by Prutha Parikh of Qualys</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2011-10-20</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2012-01-22</td></tr>
<tr><td class="cve-header">Update 2.2.22 released</td><td class="cve-value">2012-01-31</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2012-0021">low: <name name="CVE-2012-0021">mod_log_config crash</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-0021">CVE-2012-0021</a>)</h3></dt>
<dd><p>A flaw was found in mod_log_config. If the '%{cookiename}C' log format string is in use, a remote attacker could send a specific cookie causing a crash. This crash would only be a denial of service if using a threaded MPM.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2011-12-30</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2011-11-28</td></tr>
<tr><td class="cve-header">Update 2.2.22 released</td><td class="cve-value">2012-01-31</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17</td></tr>
</table></dd>
<dt><h3 id="CVE-2012-0031">low: <name name="CVE-2012-0031">scoreboard parent DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-0031">CVE-2012-0031</a>)</h3></dt>
<dd><p>A flaw was found in the handling of the scoreboard. An unprivileged child process could cause the parent process to crash at shutdown rather than terminate cleanly.</p>
<p>Acknowledgements: This issue was reported by halfdog</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2011-12-30</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2012-01-11</td></tr>
<tr><td class="cve-header">Update 2.2.22 released</td><td class="cve-value">2012-01-31</td></tr>
<tr><td class="cve-header">Update 2.0.65 released</td><td class="cve-value">2013-07-22</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.64, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2012-0053">moderate: <name name="CVE-2012-0053">error responses can expose cookies</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-0053">CVE-2012-0053</a>)</h3></dt>
<dd><p>A flaw was found in the default error response for status code 400. This flaw could be used by an attacker to expose "httpOnly" cookies when no custom ErrorDocument is specified.</p>
<p>Acknowledgements: This issue was reported by Norman Hippert</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2012-01-15</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2012-01-23</td></tr>
<tr><td class="cve-header">Update 2.2.22 released</td><td class="cve-value">2012-01-31</td></tr>
<tr><td class="cve-header">Update 2.0.65 released</td><td class="cve-value">2013-07-22</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.64, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2012-4557">low: <name name="CVE-2012-4557">mod_proxy_ajp remote DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-4557">CVE-2012-4557</a>)</h3></dt>
<dd><p>A flaw was found when mod_proxy_ajp connects to a backend server that takes too long to respond. Given a specific configuration, a remote attacker could send certain requests, putting a backend server into an error state until the retry timeout expired. This could lead to a temporary denial of service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2012-10-11</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2012-01-04</td></tr>
<tr><td class="cve-header">Update 2.2.22 released</td><td class="cve-value">2012-01-31</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.21, 2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.21">Fixed in Apache HTTP Server 2.2.21</h1><dl>

<dt><h3 id="CVE-2011-3348">moderate: <name name="CVE-2011-3348">mod_proxy_ajp remote DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-3348">CVE-2011-3348</a>)</h3></dt>
<dd><p>A flaw was found when mod_proxy_ajp is used together with mod_proxy_balancer. Given a specific configuration, a remote attacker could send certain malformed HTTP requests, putting a backend server into an error state until the retry timeout expired. This could lead to a temporary denial of service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2011-09-07</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2011-09-14</td></tr>
<tr><td class="cve-header">Update 2.2.21 released</td><td class="cve-value">2011-09-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.20, 2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.20">Fixed in Apache HTTP Server 2.2.20</h1><dl>

<dt><h3 id="CVE-2011-3192">important: <name name="CVE-2011-3192">Range header remote DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-3192">CVE-2011-3192</a>)</h3></dt>
<dd><p>A flaw was found in the way the Apache HTTP Server handled Range HTTP headers. A remote attacker could use this flaw to cause httpd to use an excessive amount of memory and CPU time via HTTP requests with a specially-crafted Range header. This could be used in a denial of service attack. Advisory: CVE-2011-3192.txt</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2011-08-20</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2011-08-20</td></tr>
<tr><td class="cve-header">Update 2.2.20 released</td><td class="cve-value">2011-08-30</td></tr>
<tr><td class="cve-header">Update 2.0.65 released</td><td class="cve-value">2013-07-12</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.64, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.19">Fixed in Apache HTTP Server 2.2.19</h1><dl>

<dt><h3 id="CVE-2011-0419">moderate: <name name="CVE-2011-0419">apr_fnmatch flaw leads to mod_autoindex remote DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-0419">CVE-2011-0419</a>)</h3></dt>
<dd><p>A flaw was found in the apr_fnmatch() function of the bundled APR library. Where mod_autoindex is enabled, and a directory indexed by mod_autoindex contained files with sufficiently long names, a remote attacker could send a carefully crafted request which would cause excessive CPU usage. This could be used in a denial of service attack.</p><p>Workaround: Setting the 'IgnoreClient' option to the 'IndexOptions' directive disables processing of the client-supplied request query arguments, preventing this attack.</p><p>Resolution: Update APR to release 1.4.5 (bundled with httpd 2.2.19) or release 0.9.20 (bundled with httpd 2.0.65)</p>
<p>Acknowledgements: This issue was reported by Maksymilian Arciemowicz</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2011-03-02</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2011-05-10</td></tr>
<tr><td class="cve-header">Update 2.2.19 released</td><td class="cve-value">2011-05-21</td></tr>
<tr><td class="cve-header">Update 2.0.65 released</td><td class="cve-value">2011-05-21</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.64, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.17">Fixed in Apache HTTP Server 2.2.17</h1><dl>

<dt><h3 id="CVE-2009-3560">low: <name name="CVE-2009-3560">expat DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-3560">CVE-2009-3560</a>)</h3></dt>
<dd><p>A buffer over-read flaw was found in the bundled expat library. An attacker who is able to get Apache to parse an untrused XML document (for example through mod_dav) may be able to cause a crash. This crash would only be a denial of service if using the worker MPM.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-12-18</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-12-02</td></tr>
<tr><td class="cve-header">Update 2.2.17 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-3720">low: <name name="CVE-2009-3720">expat DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-3720">CVE-2009-3720</a>)</h3></dt>
<dd><p>A buffer over-read flaw was found in the bundled expat library. An attacker who is able to get Apache to parse an untrused XML document (for example through mod_dav) may be able to cause a crash. This crash would only be a denial of service if using the worker MPM.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-08-21</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-01-17</td></tr>
<tr><td class="cve-header">Update 2.2.17 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2010-1623">low: <name name="CVE-2010-1623">apr_bridage_split_line DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-1623">CVE-2010-1623</a>)</h3></dt>
<dd><p>A flaw was found in the apr_brigade_split_line() function of the bundled APR-util library, used to process non-SSL requests. A remote attacker could send requests, carefully crafting the timing of individual bytes, which would slowly consume memory, potentially leading to a denial of service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2010-03-03</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2010-10-01</td></tr>
<tr><td class="cve-header">Update 2.2.17 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.16">Fixed in Apache HTTP Server 2.2.16</h1><dl>

<dt><h3 id="CVE-2010-1452">low: <name name="CVE-2010-1452">mod_cache and mod_dav DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-1452">CVE-2010-1452</a>)</h3></dt>
<dd><p>A flaw was found in the handling of requests by mod_cache (2.2) and mod_dav (2.0 and 2.2). A malicious remote attacker could send a carefully crafted request and cause a httpd child process to crash. This crash would only be a denial of service if using the worker MPM. This issue is further mitigated as mod_dav is only affected by requests that are most likely to be authenticated, and mod_cache is only affected if the uncommon "CacheIgnoreURLSessionIdentifiers" directive, introduced in version 2.2.14, is used.</p>
<p>Acknowledgements: This issue was reported by Mark Drayton.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2010-05-04</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2010-07-25</td></tr>
<tr><td class="cve-header">Update 2.2.16 released</td><td class="cve-value">2010-07-25</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2010-2068">important: <name name="CVE-2010-2068">Timeout detection flaw (mod_proxy_http)</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-2068">CVE-2010-2068</a>)</h3></dt>
<dd><p>An information disclosure flaw was found in mod_proxy_http in versions 2.2.9 through 2.2.15, 2.3.4-alpha and 2.3.5-alpha. Under certain timeout conditions, the server could return a response intended for another user. Only Windows, Netware and OS2 operating systems are affected. Only those configurations which trigger the use of proxy worker pools are affected. There was no vulnerability on earlier versions, as proxy pools were not yet introduced.</p><p>The simplest workaround is to globally configure;</p><p>SetEnv proxy-nokeepalive 1</p>
<p>Acknowledgements: We would like to thank Loren Anderson for the detailed analysis and reporting of this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2010-06-09</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2010-06-09</td></tr>
<tr><td class="cve-header">Update 2.2.16 released</td><td class="cve-value">2010-07-25</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.3.5-alpha, 2.3.4-alpha, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.15">Fixed in Apache HTTP Server 2.2.15</h1><dl>

<dt><h3 id="CVE-2010-0408">moderate: <name name="CVE-2010-0408">mod_proxy_ajp DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-0408">CVE-2010-0408</a>)</h3></dt>
<dd><p>mod_proxy_ajp would return the wrong status code if it encountered an error, causing a backend server to be put into an error state until the retry timeout expired. A remote attacker could send malicious requests to trigger this issue, resulting in denial of service.</p>
<p>Acknowledgements: We would like to thank Niku Toivola of Sulake Corporation for reporting and proposing a patch fix for this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2010-02-02</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2010-03-02</td></tr>
<tr><td class="cve-header">Update 2.2.15 released</td><td class="cve-value">2010-03-05</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2010-0425">important: <name name="CVE-2010-0425">mod_isapi module unload flaw</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-0425">CVE-2010-0425</a>)</h3></dt>
<dd><p>A flaw was found with within mod_isapi which would attempt to unload the ISAPI dll when it encountered various error states. This could leave the callbacks in an undefined state and result in a segfault. On Windows platforms using mod_isapi, a remote attacker could send a malicious request to trigger this issue, and as win32 MPM runs only one process, this would result in a denial of service, and potentially allow arbitrary code execution.</p>
<p>Acknowledgements: We would like to thank Brett Gervasoni of Sense of Security for reporting and proposing a patch fix for this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2010-02-09</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2010-03-02</td></tr>
<tr><td class="cve-header">Update 2.2.15 released</td><td class="cve-value">2010-03-05</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37</td></tr>
</table></dd>
<dt><h3 id="CVE-2010-0434">low: <name name="CVE-2010-0434">Subrequest handling of request headers (mod_headers)</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-0434">CVE-2010-0434</a>)</h3></dt>
<dd><p>A flaw in the core subrequest process code was fixed, to always provide a shallow copy of the headers_in array to the subrequest, instead of a pointer to the parent request's array as it had for requests without request bodies. This meant all modules such as mod_headers which may manipulate the input headers for a subrequest would poison the parent request in two ways, one by modifying the parent request, which might not be intended, and second by leaving pointers to modified header fields in memory allocated to the subrequest scope, which could be freed before the main request processing was finished, resulting in a segfault or in revealing data from another request on threaded servers, such as the worker or winnt MPMs.</p>
<p>Acknowledgements: We would like to thank Philip Pickett of VMware for reporting and proposing a fix for this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-12-09</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-12-09</td></tr>
<tr><td class="cve-header">Update 2.2.15 released</td><td class="cve-value">2010-03-05</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.14">Fixed in Apache HTTP Server 2.2.14</h1><dl>

<dt><h3 id="CVE-2009-2699">moderate: <name name="CVE-2009-2699">Solaris pollset DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-2699">CVE-2009-2699</a>)</h3></dt>
<dd><p>Faulty error handling was found affecting Solaris pollset support (Event Port backend) caused by a bug in APR. A remote attacker could trigger this issue on Solaris servers which used prefork or event MPMs, resulting in a denial of service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-08-05</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-09-23</td></tr>
<tr><td class="cve-header">Update 2.2.14 released</td><td class="cve-value">2009-10-05</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-3094">low: <name name="CVE-2009-3094">mod_proxy_ftp DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-3094">CVE-2009-3094</a>)</h3></dt>
<dd><p>A NULL pointer dereference flaw was found in the mod_proxy_ftp module. A malicious FTP server to which requests are being proxied could use this flaw to crash an httpd child process via a malformed reply to the EPSV or PASV commands, resulting in a limited denial of service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-09-04</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-09-02</td></tr>
<tr><td class="cve-header">Update 2.2.14 released</td><td class="cve-value">2009-10-05</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-3095">low: <name name="CVE-2009-3095">mod_proxy_ftp FTP command injection</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-3095">CVE-2009-3095</a>)</h3></dt>
<dd><p>A flaw was found in the mod_proxy_ftp module. In a reverse proxy configuration, a remote attacker could use this flaw to bypass intended access restrictions by creating a carefully-crafted HTTP Authorization header, allowing the attacker to send arbitrary commands to the FTP server.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-09-03</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-09-03</td></tr>
<tr><td class="cve-header">Update 2.2.14 released</td><td class="cve-value">2009-10-05</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.13">Fixed in Apache HTTP Server 2.2.13</h1><dl>

<dt><h3 id="CVE-2009-2412">low: <name name="CVE-2009-2412">APR apr_palloc heap overflow</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-2412">CVE-2009-2412</a>)</h3></dt>
<dd><p>A flaw in apr_palloc() in the bundled copy of APR could cause heap overflows in programs that try to apr_palloc() a user controlled size. The Apache HTTP Server itself does not pass unsanitized user-provided sizes to this function, so it could only be triggered through some other application which uses apr_palloc() in a vulnerable way.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-08-04</td></tr>
<tr><td class="cve-header">Update 2.2.13 released</td><td class="cve-value">2009-08-09</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.12">Fixed in Apache HTTP Server 2.2.12</h1><dl>

<dt><h3 id="CVE-2008-0456">low: <name name="CVE-2008-0456">CRLF injection in mod_negotiation when untrusted uploads are supported</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-0456">CVE-2008-0456</a>)</h3></dt>
<dd><p>Possible CRLF injection allowing HTTP response splitting attacks for sites which use mod_negotiation and allow untrusted uploads to locations which have MultiViews enabled.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2008-01-15</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-01-21</td></tr>
<tr><td class="cve-header">Update 2.2.12 released</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-0023">moderate: <name name="CVE-2009-0023">APR-util heap underwrite</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-0023">CVE-2009-0023</a>)</h3></dt>
<dd><p>A heap-based underwrite flaw was found in the way the bundled copy of the APR-util library created compiled forms of particular search patterns. An attacker could formulate a specially-crafted search keyword, that would overwrite arbitrary heap memory locations when processed by the pattern preparation engine.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2008-12-25</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-06-01</td></tr>
<tr><td class="cve-header">Update 2.2.12 released</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-1191">important: <name name="CVE-2009-1191">mod_proxy_ajp information disclosure</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-1191">CVE-2009-1191</a>)</h3></dt>
<dd><p>An information disclosure flaw was found in mod_proxy_ajp in version 2.2.11 only. In certain situations, if a user sent a carefully crafted HTTP request, the server could return a response intended for another user.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-03-05</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-04-21</td></tr>
<tr><td class="cve-header">Update 2.2.12 released</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.11</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-1195">low: <name name="CVE-2009-1195">AllowOverride Options handling bypass</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-1195">CVE-2009-1195</a>)</h3></dt>
<dd><p>A flaw was found in the handling of the "Options" and "AllowOverride" directives. In configurations using the "AllowOverride" directive with certain "Options=" arguments, local users were not restricted from executing commands from a Server-Side-Include script as intended.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-03-09</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-04-22</td></tr>
<tr><td class="cve-header">Update 2.2.12 released</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-1890">important: <name name="CVE-2009-1890">mod_proxy reverse proxy DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-1890">CVE-2009-1890</a>)</h3></dt>
<dd><p>A denial of service flaw was found in the mod_proxy module when it was used as a reverse proxy. A remote attacker could use this flaw to force a proxy process to consume large amounts of CPU time.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-06-30</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-07-02</td></tr>
<tr><td class="cve-header">Update 2.2.12 released</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-1891">low: <name name="CVE-2009-1891">mod_deflate DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-1891">CVE-2009-1891</a>)</h3></dt>
<dd><p>A denial of service flaw was found in the mod_deflate module. This module continued to compress large files until compression was complete, even if the network connection that requested the content was closed before compression completed. This would cause mod_deflate to consume large amounts of CPU if mod_deflate was enabled for a large file.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-06-26</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-06-26</td></tr>
<tr><td class="cve-header">Update 2.2.12 released</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-1955">moderate: <name name="CVE-2009-1955">APR-util XML DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-1955">CVE-2009-1955</a>)</h3></dt>
<dd><p>A denial of service flaw was found in the bundled copy of the APR-util library Extensible Markup Language (XML) parser. A remote attacker could create a specially-crafted XML document that would cause excessive memory consumption when processed by the XML decoding engine.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-06-06</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-06-01</td></tr>
<tr><td class="cve-header">Update 2.2.12 released</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2009-1956">moderate: <name name="CVE-2009-1956">APR-util off-by-one overflow</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-1956">CVE-2009-1956</a>)</h3></dt>
<dd><p>An off-by-one overflow flaw was found in the way the bundled copy of the APR-util library processed a variable list of arguments. An attacker could provide a specially-crafted string as input for the formatted output conversion routine, which could, on big-endian platforms, potentially lead to the disclosure of sensitive information or a denial of service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-04-24</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-04-24</td></tr>
<tr><td class="cve-header">Update 2.2.12 released</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.10">Fixed in Apache HTTP Server 2.2.10</h1><dl>

<dt><h3 id="CVE-2008-2939">low: <name name="CVE-2008-2939">mod_proxy_ftp globbing XSS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-2939">CVE-2008-2939</a>)</h3></dt>
<dd><p>A flaw was found in the handling of wildcards in the path of a FTP URL with mod_proxy_ftp. If mod_proxy_ftp is enabled to support FTP-over-HTTP, requests containing globbing characters could lead to cross-site scripting (XSS) attacks.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2008-07-28</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-08-05</td></tr>
<tr><td class="cve-header">Update 2.2.10 released</td><td class="cve-value">2008-10-31</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2010-2791">important: <name name="CVE-2010-2791">Timeout detection flaw (mod_proxy_http)</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-2791">CVE-2010-2791</a>)</h3></dt>
<dd><p>An information disclosure flaw was found in mod_proxy_http in version 2.2.9 only, on Unix platforms. Under certain timeout conditions, the server could return a response intended for another user. Only those configurations which trigger the use of proxy worker pools are affected. There was no vulnerability on earlier versions, as proxy pools were not yet introduced. The simplest workaround is to globally configure:</p><p>SetEnv proxy-nokeepalive 1</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2010-07-23</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2010-07-23</td></tr>
<tr><td class="cve-header">Update 2.2.10 released</td><td class="cve-value">2008-10-31</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.9</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.9">Fixed in Apache HTTP Server 2.2.9</h1><dl>

<dt><h3 id="CVE-2007-6420">low: <name name="CVE-2007-6420">mod_proxy_balancer CSRF</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-6420">CVE-2007-6420</a>)</h3></dt>
<dd><p>The mod_proxy_balancer provided an administrative interface that could be vulnerable to cross-site request forgery (CSRF) attacks.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2007-10-12</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-01-09</td></tr>
<tr><td class="cve-header">Update 2.2.9 released</td><td class="cve-value">2008-06-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2008-2364">moderate: <name name="CVE-2008-2364">mod_proxy_http DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-2364">CVE-2008-2364</a>)</h3></dt>
<dd><p>A flaw was found in the handling of excessive interim responses from an origin server when using mod_proxy_http. A remote attacker could cause a denial of service or high memory usage.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2008-05-29</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-06-10</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Update 2.2.9 released</td><td class="cve-value">2008-06-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.8">Fixed in Apache HTTP Server 2.2.8</h1><dl>

<dt><h3 id="CVE-2007-5000">moderate: <name name="CVE-2007-5000">mod_imagemap XSS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-5000">CVE-2007-5000</a>)</h3></dt>
<dd><p>A flaw was found in the mod_imagemap module. On sites where mod_imagemap is enabled and an imagemap file is publicly available, a cross-site scripting attack is possible.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2007-10-23</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2007-12-11</td></tr>
<tr><td class="cve-header">Update 2.2.8 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Update 2.0.63 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Update 1.3.41 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.39, 1.3.37, 1.3.36, 1.3.35, 1.3.34, 1.3.33, 1.3.32, 1.3.31, 1.3.29, 1.3.28, 1.3.27, 1.3.26, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2, 1.3.1, 1.3.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2007-6388">moderate: <name name="CVE-2007-6388">mod_status XSS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-6388">CVE-2007-6388</a>)</h3></dt>
<dd><p>A flaw was found in the mod_status module. On sites where mod_status is enabled and the status pages were publicly accessible, a cross-site scripting attack is possible. Note that the server-status page is not enabled by default and it is best practice to not make this publicly available.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2007-12-15</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-01-02</td></tr>
<tr><td class="cve-header">Update 2.2.8 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Update 2.0.63 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Update 1.3.41 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.39, 1.3.37, 1.3.36, 1.3.35, 1.3.34, 1.3.33, 1.3.32, 1.3.31, 1.3.29, 1.3.28, 1.3.27, 1.3.26, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2</td></tr>
</table></dd>
<dt><h3 id="CVE-2007-6421">low: <name name="CVE-2007-6421">mod_proxy_balancer XSS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-6421">CVE-2007-6421</a>)</h3></dt>
<dd><p>A flaw was found in the mod_proxy_balancer module. On sites where mod_proxy_balancer is enabled, a cross-site scripting attack against an authorized user is possible.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2007-12-12</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-01-02</td></tr>
<tr><td class="cve-header">Update 2.2.8 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2007-6422">low: <name name="CVE-2007-6422">mod_proxy_balancer DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-6422">CVE-2007-6422</a>)</h3></dt>
<dd><p>A flaw was found in the mod_proxy_balancer module. On sites where mod_proxy_balancer is enabled, an authorized user could send a carefully crafted request that would cause the Apache child process handling that request to crash. This could lead to a denial of service if using a threaded Multi-Processing Module.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2007-12-12</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-01-02</td></tr>
<tr><td class="cve-header">Update 2.2.8 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2008-0005">low: <name name="CVE-2008-0005">mod_proxy_ftp UTF-7 XSS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-0005">CVE-2008-0005</a>)</h3></dt>
<dd><p>A workaround was added in the mod_proxy_ftp module. On sites where mod_proxy_ftp is enabled and a forward proxy is configured, a cross-site scripting attack is possible against Web browsers which do not correctly derive the response character set following the rules in RFC 2616.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2007-12-15</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-01-08</td></tr>
<tr><td class="cve-header">Update 2.0.63 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Update 2.2.8 released</td><td class="cve-value">2008-01-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.6">Fixed in Apache HTTP Server 2.2.6</h1><dl>

<dt><h3 id="CVE-2006-5752">moderate: <name name="CVE-2006-5752">mod_status cross-site scripting</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2006-5752">CVE-2006-5752</a>)</h3></dt>
<dd><p>A flaw was found in the mod_status module. On sites where the server-status page is publicly accessible and ExtendedStatus is enabled this could lead to a cross-site scripting attack. Note that the server-status page is not enabled by default and it is best practice to not make this publicly available.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2006-10-19</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2007-06-20</td></tr>
<tr><td class="cve-header">Update 1.3.39 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Update 2.0.61 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Update 2.2.6 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.37, 1.3.36, 1.3.35, 1.3.34, 1.3.33, 1.3.32, 1.3.31, 1.3.29, 1.3.28, 1.3.27, 1.3.26, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2</td></tr>
</table></dd>
<dt><h3 id="CVE-2007-1862">moderate: <name name="CVE-2007-1862">mod_cache information leak</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-1862">CVE-2007-1862</a>)</h3></dt>
<dd><p>The recall_headers function in mod_mem_cache in Apache 2.2.4 did not properly copy all levels of header data, which can cause Apache to return HTTP headers containing previously used data, which could be used by remote attackers to obtain potentially sensitive information.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2007-04-26</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2007-06-01</td></tr>
<tr><td class="cve-header">Update 2.2.6 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.4</td></tr>
</table></dd>
<dt><h3 id="CVE-2007-1863">moderate: <name name="CVE-2007-1863">mod_cache proxy DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-1863">CVE-2007-1863</a>)</h3></dt>
<dd><p>A bug was found in the mod_cache module. On sites where caching is enabled, a remote attacker could send a carefully crafted request that would cause the Apache child process handling that request to crash. This could lead to a denial of service if using a threaded Multi-Processing Module.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2007-05-02</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2007-06-18</td></tr>
<tr><td class="cve-header">Update 2.0.61 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Update 2.2.6 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37</td></tr>
</table></dd>
<dt><h3 id="CVE-2007-3304">moderate: <name name="CVE-2007-3304">Signals to arbitrary processes</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-3304">CVE-2007-3304</a>)</h3></dt>
<dd><p>The Apache HTTP server did not verify that a process was an Apache child process before sending it signals. A local attacker with the ability to run scripts on the HTTP server could manipulate the scoreboard and cause arbitrary processes to be terminated which could lead to a denial of service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2006-05-15</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2007-06-19</td></tr>
<tr><td class="cve-header">Update 2.0.61 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Update 2.2.6 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Update 1.3.39 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.37, 1.3.36, 1.3.35, 1.3.34, 1.3.33, 1.3.32, 1.3.31, 1.3.29, 1.3.28, 1.3.27, 1.3.26, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2, 1.3.1, 1.3.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2007-3847">moderate: <name name="CVE-2007-3847">mod_proxy crash</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-3847">CVE-2007-3847</a>)</h3></dt>
<dd><p>A flaw was found in the Apache HTTP Server mod_proxy module. On sites where a reverse proxy is configured, a remote attacker could send a carefully crafted request that would cause the Apache child process handling that request to crash. On sites where a forward proxy is configured, an attacker could cause a similar crash if a user could be persuaded to visit a malicious site using the proxy. This could lead to a denial of service if using a threaded Multi-Processing Module.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2006-12-10</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2006-12-10</td></tr>
<tr><td class="cve-header">Update 2.2.6 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Update 2.0.61 released</td><td class="cve-value">2007-09-07</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.3">Fixed in Apache HTTP Server 2.2.3</h1><dl>

<dt><h3 id="CVE-2006-3747">important: <name name="CVE-2006-3747">mod_rewrite off-by-one error</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2006-3747">CVE-2006-3747</a>)</h3></dt>
<dd><p>An off-by-one flaw exists in the Rewrite module, mod_rewrite. Depending on the manner in which Apache httpd was compiled, this software defect may result in a vulnerability which, in combination with certain types of Rewrite rules in the web server configuration files, could be triggered remotely. For vulnerable builds, the nature of the vulnerability can be denial of service (crashing of web server processes) or potentially allow arbitrary code execution.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2006-07-21</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2006-07-27</td></tr>
<tr><td class="cve-header">Update 2.2.3 released</td><td class="cve-value">2006-07-27</td></tr>
<tr><td class="cve-header">Update 2.0.59 released</td><td class="cve-value">2006-07-27</td></tr>
<tr><td class="cve-header">Update 1.3.37 released</td><td class="cve-value">2006-07-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.2, 2.2.0, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 1.3.36, 1.3.35, 1.3.34, 1.3.33, 1.3.32, 1.3.31, 1.3.29, 1.3.28</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.2.2">Fixed in Apache HTTP Server 2.2.2</h1><dl>

<dt><h3 id="CVE-2005-3352">moderate: <name name="CVE-2005-3352">mod_imap Referer Cross-Site Scripting</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2005-3352">CVE-2005-3352</a>)</h3></dt>
<dd><p>A flaw in mod_imap when using the Referer directive with image maps. In certain site configurations a remote attacker could perform a cross-site scripting attack if a victim can be forced to visit a malicious URL using certain web browsers.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2005-11-01</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2005-12-12</td></tr>
<tr><td class="cve-header">Update 2.2.2 released</td><td class="cve-value">2006-05-01</td></tr>
<tr><td class="cve-header">Update 2.0.58 released</td><td class="cve-value">2006-05-01</td></tr>
<tr><td class="cve-header">Update 1.3.35 released</td><td class="cve-value">2006-05-01</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.0, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.34, 1.3.33, 1.3.32, 1.3.31, 1.3.29, 1.3.28, 1.3.27, 1.3.26, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2, 1.3.1, 1.3.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2005-3357">low: <name name="CVE-2005-3357">mod_ssl access control DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2005-3357">CVE-2005-3357</a>)</h3></dt>
<dd><p>A NULL pointer dereference flaw in mod_ssl was discovered affecting server configurations where an SSL virtual host is configured with access control and a custom 400 error document. A remote attacker could send a carefully crafted request to trigger this issue which would lead to a crash. This crash would only be a denial of service if using the worker MPM.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2005-12-05</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2005-12-12</td></tr>
<tr><td class="cve-header">Update 2.2.2 released</td><td class="cve-value">2006-05-01</td></tr>
<tr><td class="cve-header">Update 2.0.58 released</td><td class="cve-value">2006-05-01</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.0, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>