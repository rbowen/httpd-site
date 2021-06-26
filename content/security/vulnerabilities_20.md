Title: Apache HTTP Server 2.0 vulnerabilities

<h1>Apache HTTP Server 2.0 vulnerabilities</h1>
<p>This page lists all security vulnerabilities fixed in released versions of Apache HTTP Server 2.0. Each vulnerability is given a security <a href="/security/impact_levels.html">impact rating</a> by the Apache security team - please note that this rating may well vary from platform to platform.  We also list the versions the flaw is known to affect, and where a flaw has not been verified list the version with a question mark.</p>
<p>Please note that if a vulnerability is shown below as being fixed in a "-dev" release then this means that a fix has been applied to the development source tree and will be part of an upcoming full release.</p>
<p>Please send comments or corrections for these vulnerabilities to the <a href="/security_report.html">Security Team</a>.</p> <br/>
<p><h3>Apache httpd 2.0 has had no new releases since 2013 and should not be used.   This page only lists security issues that occurred before August 2013.  Subsequent issues may have affected 2.0 but will not be investigated or listed here.  Users are advised to upgrade to the currently supported released version to address known issues.</h3></p><br/>

<h1 id="2.0.65">Fixed in Apache HTTP Server 2.0.65</h1><dl>

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
<dt><h3 id="CVE-2011-3192">important: <name name="CVE-2011-3192">Range header remote DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-3192">CVE-2011-3192</a>)</h3></dt>
<dd><p>A flaw was found in the way the Apache HTTP Server handled Range HTTP headers. A remote attacker could use this flaw to cause httpd to use an excessive amount of memory and CPU time via HTTP requests with a specially-crafted Range header. This could be used in a denial of service attack. Advisory: CVE-2011-3192.txt</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2011-08-20</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2011-08-20</td></tr>
<tr><td class="cve-header">Update 2.2.20 released</td><td class="cve-value">2011-08-30</td></tr>
<tr><td class="cve-header">Update 2.0.65 released</td><td class="cve-value">2013-07-12</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.19, 2.2.18, 2.2.17, 2.2.16, 2.2.15, 2.2.14, 2.2.13, 2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.64, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
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
</dl></br/>

<h1 id="2.0.64">Fixed in Apache HTTP Server 2.0.64</h1><dl>

<dt><h3 id="CVE-2008-2364">moderate: <name name="CVE-2008-2364">mod_proxy_http DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-2364">CVE-2008-2364</a>)</h3></dt>
<dd><p>A flaw was found in the handling of excessive interim responses from an origin server when using mod_proxy_http. A remote attacker could cause a denial of service or high memory usage.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2008-05-29</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-06-10</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Update 2.2.9 released</td><td class="cve-value">2008-06-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2008-2939">low: <name name="CVE-2008-2939">mod_proxy_ftp globbing XSS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-2939">CVE-2008-2939</a>)</h3></dt>
<dd><p>A flaw was found in the handling of wildcards in the path of a FTP URL with mod_proxy_ftp. If mod_proxy_ftp is enabled to support FTP-over-HTTP, requests containing globbing characters could lead to cross-site scripting (XSS) attacks.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2008-07-28</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2008-08-05</td></tr>
<tr><td class="cve-header">Update 2.2.10 released</td><td class="cve-value">2008-10-31</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
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
<dt><h3 id="CVE-2009-2412">low: <name name="CVE-2009-2412">APR apr_palloc heap overflow</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-2412">CVE-2009-2412</a>)</h3></dt>
<dd><p>A flaw in apr_palloc() in the bundled copy of APR could cause heap overflows in programs that try to apr_palloc() a user controlled size. The Apache HTTP Server itself does not pass unsanitized user-provided sizes to this function, so it could only be triggered through some other application which uses apr_palloc() in a vulnerable way.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2009-07-27</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2009-08-04</td></tr>
<tr><td class="cve-header">Update 2.2.13 released</td><td class="cve-value">2009-08-09</td></tr>
<tr><td class="cve-header">Update 2.0.64 released</td><td class="cve-value">2010-10-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.2.12, 2.2.11, 2.2.10, 2.2.9, 2.2.8, 2.2.6, 2.2.5, 2.2.4, 2.2.3, 2.2.2, 2.2.0, 2.0.63, 2.0.61, 2.0.59, 2.0.58, 2.0.55, 2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
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

<h1 id="2.0.63">Fixed in Apache HTTP Server 2.0.63</h1><dl>

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

<h1 id="2.0.61">Fixed in Apache HTTP Server 2.0.61</h1><dl>

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

<h1 id="2.0.59">Fixed in Apache HTTP Server 2.0.59</h1><dl>

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

<h1 id="2.0.58">Fixed in Apache HTTP Server 2.0.58</h1><dl>

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

<h1 id="2.0.55">Fixed in Apache HTTP Server 2.0.55</h1><dl>

<dt><h3 id="CVE-2005-1268">low: <name name="CVE-2005-1268">Malicious CRL off-by-one</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2005-1268">CVE-2005-1268</a>)</h3></dt>
<dd><p>An off-by-one stack overflow was discovered in the mod_ssl CRL verification callback. In order to exploit this issue the Apache server would need to be configured to use a malicious certificate revocation list (CRL)</p>
<table class="cve"><tr><td class="cve-header">Issue public</td><td class="cve-value">2005-06-08</td></tr>
<tr><td class="cve-header">Update 2.0.55 released</td><td class="cve-value">2005-10-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2005-2088">moderate: <name name="CVE-2005-2088">HTTP Request Spoofing</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2005-2088">CVE-2005-2088</a>)</h3></dt>
<dd><p>A flaw occured when using the Apache server as a HTTP proxy. A remote attacker could send a HTTP request with both a "Transfer-Encoding: chunked" header and a Content-Length header, causing Apache to incorrectly handle and forward the body of the request in a way that causes the receiving server to process it as a separate HTTP request. This could allow the bypass of web application firewall protection or lead to cross-site scripting (XSS) attacks.</p>
<table class="cve"><tr><td class="cve-header">Issue public</td><td class="cve-value">2005-06-11</td></tr>
<tr><td class="cve-header">Update 2.0.55 released</td><td class="cve-value">2005-10-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2005-2491">low: <name name="CVE-2005-2491">PCRE overflow</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2005-2491">CVE-2005-2491</a>)</h3></dt>
<dd><p>An integer overflow flaw was found in PCRE, a Perl-compatible regular expression library included within httpd. A local user who has the ability to create .htaccess files could create a maliciously crafted regular expression in such as way that they could gain the privileges of a httpd child.</p>
<table class="cve"><tr><td class="cve-header">Issue public</td><td class="cve-value">2005-08-01</td></tr>
<tr><td class="cve-header">Update 2.0.55 released</td><td class="cve-value">2005-10-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2005-2700">important: <name name="CVE-2005-2700">SSLVerifyClient bypass</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2005-2700">CVE-2005-2700</a>)</h3></dt>
<dd><p>A flaw in the mod_ssl handling of the "SSLVerifyClient" directive. This flaw would occur if a virtual host has been configured using "SSLVerifyClient optional" and further a directive "SSLVerifyClient required" is set for a specific location. For servers configured in this fashion, an attacker may be able to access resources that should otherwise be protected, by not supplying a client certificate when connecting.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2005-08-30</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2005-08-30</td></tr>
<tr><td class="cve-header">Update 2.0.55 released</td><td class="cve-value">2005-10-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2005-2728">moderate: <name name="CVE-2005-2728">Byterange filter DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2005-2728">CVE-2005-2728</a>)</h3></dt>
<dd><p>A flaw in the byterange filter would cause some responses to be buffered into memory. If a server has a dynamic resource such as a CGI script or PHP script which generates a large amount of data, an attacker could send carefully crafted requests in order to consume resources, potentially leading to a Denial of Service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2005-07-07</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2005-07-07</td></tr>
<tr><td class="cve-header">Update 2.0.55 released</td><td class="cve-value">2005-10-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2005-2970">low: <name name="CVE-2005-2970">Worker MPM memory leak</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2005-2970">CVE-2005-2970</a>)</h3></dt>
<dd><p>A memory leak in the worker MPM would allow remote attackers to cause a denial of service (memory consumption) via aborted connections, which prevents the memory for the transaction pool from being reused for other connections. This issue was downgraded in severity to low (from moderate) as sucessful exploitation of the race condition would be difficult.</p>
<table class="cve"><tr><td class="cve-header">Update 2.0.55 released</td><td class="cve-value">2005-10-14</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.54, 2.0.53, 2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.53">Fixed in Apache HTTP Server 2.0.53</h1><dl>

<dt><h3 id="CVE-2004-0885">moderate: <name name="CVE-2004-0885">SSLCipherSuite bypass</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0885">CVE-2004-0885</a>)</h3></dt>
<dd><p>An issue has been discovered in the mod_ssl module when configured to use the "SSLCipherSuite" directive in directory or location context. If a particular location context has been configured to require a specific set of cipher suites, then a client will be able to access that location using any cipher suite allowed by the virtual host configuration.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-10-01</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-10-01</td></tr>
<tr><td class="cve-header">Update 2.0.53 released</td><td class="cve-value">2005-02-08</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2004-0942">important: <name name="CVE-2004-0942">Memory consumption DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0942">CVE-2004-0942</a>)</h3></dt>
<dd><p>An issue was discovered where the field length limit was not enforced for certain malicious requests. This could allow a remote attacker who is able to send large amounts of data to a server the ability to cause Apache children to consume proportional amounts of memory, leading to a denial of service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-10-28</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-11-01</td></tr>
<tr><td class="cve-header">Update 2.0.53 released</td><td class="cve-value">2005-02-08</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2004-1834">low: <name name="CVE-2004-1834">mod_disk_cache stores sensitive headers</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-1834">CVE-2004-1834</a>)</h3></dt>
<dd><p>The experimental mod_disk_cache module stored client authentication credentials for cached objects such as proxy authentication credentials and Basic Authentication passwords on disk.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-03-02</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-03-20</td></tr>
<tr><td class="cve-header">Update 2.0.53 released</td><td class="cve-value">2005-02-08</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.52, 2.0.51, 2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.52">Fixed in Apache HTTP Server 2.0.52</h1><dl>

<dt><h3 id="CVE-2004-0811">important: <name name="CVE-2004-0811">Basic authentication bypass</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0811">CVE-2004-0811</a>)</h3></dt>
<dd><p>A flaw in Apache 2.0.51 (only) broke the merging of the Satisfy directive which could result in access being granted to resources despite any configured authentication</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-09-18</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-09-18</td></tr>
<tr><td class="cve-header">Update 2.0.52 released</td><td class="cve-value">2004-09-28</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.51</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.51">Fixed in Apache HTTP Server 2.0.51</h1><dl>

<dt><h3 id="CVE-2004-0747">low: <name name="CVE-2004-0747">Environment variable expansion flaw</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0747">CVE-2004-0747</a>)</h3></dt>
<dd><p>A buffer overflow was found in the expansion of environment variables during configuration file parsing. This issue could allow a local user to gain the privileges of a httpd child if a server can be forced to parse a carefully crafted .htaccess file written by a local user.</p>
<p>Acknowledgements: We would like to thank the Swedish IT Incident Centre (SITIC) for reporting this issue.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-08-05</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-09-15</td></tr>
<tr><td class="cve-header">Update 2.0.51 released</td><td class="cve-value">2004-09-15</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2004-0748">important: <name name="CVE-2004-0748">SSL connection infinite loop</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0748">CVE-2004-0748</a>)</h3></dt>
<dd><p>An issue was discovered in the mod_ssl module in Apache 2.0. A remote attacker who forces an SSL connection to be aborted in a particular state may cause an Apache child process to enter an infinite loop, consuming CPU resources.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-07-07</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-07-07</td></tr>
<tr><td class="cve-header">Update 2.0.51 released</td><td class="cve-value">2004-09-15</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.50, 2.0.49?, 2.0.48?, 2.0.47?, 2.0.46?, 2.0.45?, 2.0.44?, 2.0.43?, 2.0.42?, 2.0.40?, 2.0.39?, 2.0.37?, 2.0.36?, 2.0.35?</td></tr>
</table></dd>
<dt><h3 id="CVE-2004-0751">low: <name name="CVE-2004-0751">Malicious SSL proxy can cause crash</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0751">CVE-2004-0751</a>)</h3></dt>
<dd><p>An issue was discovered in the mod_ssl module in Apache 2.0.44-2.0.50 which could be triggered if the server is configured to allow proxying to a remote SSL server. A malicious remote SSL server could force an httpd child process to crash by sending a carefully crafted response header. This issue is not believed to allow execution of arbitrary code and will only result in a denial of service where a threaded process model is in use.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-07-07</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-07-07</td></tr>
<tr><td class="cve-header">Update 2.0.51 released</td><td class="cve-value">2004-09-15</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44</td></tr>
</table></dd>
<dt><h3 id="CVE-2004-0786">critical: <name name="CVE-2004-0786">IPv6 URI parsing heap overflow</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0786">CVE-2004-0786</a>)</h3></dt>
<dd><p>Testing using the Codenomicon HTTP Test Tool performed by the Apache Software Foundation security group and Red Hat uncovered an input validation issue in the IPv6 URI parsing routines in the apr-util library. If a remote attacker sent a request including a carefully crafted URI, an httpd child process could be made to crash. One some BSD systems it is believed this flaw may be able to lead to remote code execution.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-08-25</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-09-15</td></tr>
<tr><td class="cve-header">Update 2.0.51 released</td><td class="cve-value">2004-09-15</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2004-0809">low: <name name="CVE-2004-0809">WebDAV remote crash</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0809">CVE-2004-0809</a>)</h3></dt>
<dd><p>An issue was discovered in the mod_dav module which could be triggered for a location where WebDAV authoring access has been configured. A malicious remote client which is authorized to use the LOCK method could force an httpd child process to crash by sending a particular sequence of LOCK requests. This issue does not allow execution of arbitrary code. and will only result in a denial of service where a threaded process model is in use.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-09-12</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-09-12</td></tr>
<tr><td class="cve-header">Update 2.0.51 released</td><td class="cve-value">2004-09-15</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.50, 2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.50">Fixed in Apache HTTP Server 2.0.50</h1><dl>

<dt><h3 id="CVE-2004-0488">low: <name name="CVE-2004-0488">FakeBasicAuth overflow</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0488">CVE-2004-0488</a>)</h3></dt>
<dd><p>A buffer overflow in the mod_ssl FakeBasicAuth code could be exploited by an attacker using a (trusted) client certificate with a subject DN field which exceeds 6K in length.</p>
<table class="cve"><tr><td class="cve-header">Issue public</td><td class="cve-value">2004-05-17</td></tr>
<tr><td class="cve-header">Update 2.0.50 released</td><td class="cve-value">2004-07-01</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.49, 2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2004-0493">important: <name name="CVE-2004-0493">Header parsing memory leak</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0493">CVE-2004-0493</a>)</h3></dt>
<dd><p>A memory leak in parsing of HTTP headers which can be triggered remotely may allow a denial of service attack due to excessive memory consumption.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-06-13</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-07-01</td></tr>
<tr><td class="cve-header">Update 2.0.50 released</td><td class="cve-value">2004-07-01</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.49, 2.0.48?, 2.0.47?, 2.0.46?, 2.0.45?, 2.0.44?, 2.0.43?, 2.0.42?, 2.0.40?, 2.0.39?, 2.0.37?, 2.0.36?, 2.0.35?</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.49">Fixed in Apache HTTP Server 2.0.49</h1><dl>

<dt><h3 id="CVE-2003-0020">low: <name name="CVE-2003-0020">Error log escape filtering</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0020">CVE-2003-0020</a>)</h3></dt>
<dd><p>Apache does not filter terminal escape sequences from error logs, which could make it easier for attackers to insert those sequences into terminal emulators containing vulnerabilities related to escape sequences.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2003-02-24</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-02-24</td></tr>
<tr><td class="cve-header">Update 1.3.31 released</td><td class="cve-value">2004-05-12</td></tr>
<tr><td class="cve-header">Update 2.0.49 released</td><td class="cve-value">2004-03-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.29, 1.3.28, 1.3.27, 1.3.26, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2, 1.3.1, 1.3.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2004-0113">important: <name name="CVE-2004-0113">mod_ssl memory leak</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0113">CVE-2004-0113</a>)</h3></dt>
<dd><p>A memory leak in mod_ssl allows a remote denial of service attack against an SSL-enabled server by sending plain HTTP requests to the SSL port.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-02-20</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-02-20</td></tr>
<tr><td class="cve-header">Update 2.0.49 released</td><td class="cve-value">2004-03-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2004-0174">important: <name name="CVE-2004-0174">listening socket starvation</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0174">CVE-2004-0174</a>)</h3></dt>
<dd><p>A starvation issue on listening sockets occurs when a short-lived connection on a rarely-accessed listening socket will cause a child to hold the accept mutex and block out new connections until another connection arrives on that rarely-accessed listening socket. This issue is known to affect some versions of AIX, Solaris, and Tru64; it is known to not affect FreeBSD or Linux.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2004-02-25</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2004-03-18</td></tr>
<tr><td class="cve-header">Update 1.3.31 released</td><td class="cve-value">2004-05-12</td></tr>
<tr><td class="cve-header">Update 2.0.49 released</td><td class="cve-value">2004-03-19</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.48, 2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.29, 1.3.28?, 1.3.27?, 1.3.26?, 1.3.24?, 1.3.22?, 1.3.20?, 1.3.19?, 1.3.17?, 1.3.14?, 1.3.12?, 1.3.11?, 1.3.9?, 1.3.6?, 1.3.4?, 1.3.3?, 1.3.2?, 1.3.1?, 1.3.0?</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.48">Fixed in Apache HTTP Server 2.0.48</h1><dl>

<dt><h3 id="CVE-2003-0542">low: <name name="CVE-2003-0542">Local configuration regular expression overflow</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0542">CVE-2003-0542</a>)</h3></dt>
<dd><p>By using a regular expression with more than 9 captures a buffer overflow can occur in mod_alias or mod_rewrite. To exploit this an attacker would need to be able to create a carefully crafted configuration file (.htaccess or httpd.conf)</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2003-08-04</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-10-27</td></tr>
<tr><td class="cve-header">Update 1.3.29 released</td><td class="cve-value">2003-10-27</td></tr>
<tr><td class="cve-header">Update 2.0.48 released</td><td class="cve-value">2003-10-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.28, 1.3.27, 1.3.26, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2, 1.3.1, 1.3.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2003-0789">moderate: <name name="CVE-2003-0789">CGI output information leak</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0789">CVE-2003-0789</a>)</h3></dt>
<dd><p>A bug in mod_cgid mishandling of CGI redirect paths can result in CGI output going to the wrong client when a threaded MPM is used.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2003-10-03</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-10-27</td></tr>
<tr><td class="cve-header">Update 2.0.48 released</td><td class="cve-value">2003-10-27</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.47, 2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.47">Fixed in Apache HTTP Server 2.0.47</h1><dl>

<dt><h3 id="CVE-2003-0192">low: <name name="CVE-2003-0192">mod_ssl renegotiation issue</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0192">CVE-2003-0192</a>)</h3></dt>
<dd><p>A bug in the optional renegotiation code in mod_ssl included with Apache httpd can cause cipher suite restrictions to be ignored. This is triggered if optional renegotiation is used (SSLOptions +OptRenegotiate) along with verification of client certificates and a change to the cipher suite over the renegotiation.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2003-04-30</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-07-09</td></tr>
<tr><td class="cve-header">Update 2.0.47 released</td><td class="cve-value">2003-07-09</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2003-0253">important: <name name="CVE-2003-0253">Remote DoS with multiple Listen directives</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0253">CVE-2003-0253</a>)</h3></dt>
<dd><p>In a server with multiple listening sockets a certain error returned by accept() on a rarely access port can cause a temporary denial of service, due to a bug in the prefork MPM.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2003-06-25</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-07-09</td></tr>
<tr><td class="cve-header">Update 2.0.47 released</td><td class="cve-value">2003-07-09</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
<dt><h3 id="CVE-2003-0254">moderate: <name name="CVE-2003-0254">Remote DoS via IPv6 ftp proxy</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0254">CVE-2003-0254</a>)</h3></dt>
<dd><p>When a client requests that proxy ftp connect to a ftp server with IPv6 address, and the proxy is unable to create an IPv6 socket, an infinite loop occurs causing a remote Denial of Service.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2003-06-25</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-07-09</td></tr>
<tr><td class="cve-header">Update 2.0.47 released</td><td class="cve-value">2003-07-09</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.46, 2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.46">Fixed in Apache HTTP Server 2.0.46</h1><dl>

<dt><h3 id="CVE-2003-0083">low: <name name="CVE-2003-0083">Filtered escape sequences</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0083">CVE-2003-0083</a>)</h3></dt>
<dd><p>Apache did not filter terminal escape sequences from its access logs, which could make it easier for attackers to insert those sequences into terminal emulators containing vulnerabilities related to escape sequences.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2003-02-24</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-02-24</td></tr>
<tr><td class="cve-header">Update 2.0.46 released</td><td class="cve-value">2004-04-02</td></tr>
<tr><td class="cve-header">Update 1.3.26 released</td><td class="cve-value">2002-06-18</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2, 1.3.1, 1.3.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2003-0134">important: <name name="CVE-2003-0134">OS2 device name DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0134">CVE-2003-0134</a>)</h3></dt>
<dd><p>Apache on OS2 up to and including Apache 2.0.45 have a Denial of Service vulnerability caused by device names.</p>
<table class="cve"><tr><td class="cve-header">Issue public</td><td class="cve-value">2003-03-31</td></tr>
<tr><td class="cve-header">Update 2.0.46 released</td><td class="cve-value">2003-05-28</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.45, 2.0.44?, 2.0.43?, 2.0.42?, 2.0.40?, 2.0.39?, 2.0.37?, 2.0.36?, 2.0.35?</td></tr>
</table></dd>
<dt><h3 id="CVE-2003-0189">important: <name name="CVE-2003-0189">Basic Authentication DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0189">CVE-2003-0189</a>)</h3></dt>
<dd><p>A build system problem in Apache 2.0.40 through 2.0.45 allows remote attackers to cause a denial of access to authenticated content when a threaded server is used.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2003-04-25</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-05-28</td></tr>
<tr><td class="cve-header">Update 2.0.46 released</td><td class="cve-value">2003-05-28</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40</td></tr>
</table></dd>
<dt><h3 id="CVE-2003-0245">critical: <name name="CVE-2003-0245">APR remote crash</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0245">CVE-2003-0245</a>)</h3></dt>
<dd><p>A vulnerability in the apr_psprintf function in the Apache Portable Runtime (APR) library allows remote attackers to cause a denial of service (crash) and possibly execute arbitrary code via long strings, as demonstrated using XML objects to mod_dav, and possibly other vectors.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2003-04-09</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-05-28</td></tr>
<tr><td class="cve-header">Update 2.0.46 released</td><td class="cve-value">2003-05-28</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.45, 2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.45">Fixed in Apache HTTP Server 2.0.45</h1><dl>

<dt><h3 id="CVE-2003-0132">important: <name name="CVE-2003-0132">Line feed memory leak DoS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0132">CVE-2003-0132</a>)</h3></dt>
<dd><p>Apache 2.0 versions before Apache 2.0.45 had a significant Denial of Service vulnerability. Remote attackers could cause a denial of service (memory consumption) via large chunks of linefeed characters, which causes Apache to allocate 80 bytes for each linefeed.</p>
<table class="cve"><tr><td class="cve-header">Issue public</td><td class="cve-value">2004-04-02</td></tr>
<tr><td class="cve-header">Update 2.0.45 released</td><td class="cve-value">2004-04-02</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.44, 2.0.43, 2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.44">Fixed in Apache HTTP Server 2.0.44</h1><dl>

<dt><h3 id="CVE-2003-0016">critical: <name name="CVE-2003-0016">MS-DOS device name filtering</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0016">CVE-2003-0016</a>)</h3></dt>
<dd><p>On Windows platforms Apache did not correctly filter MS-DOS device names which could lead to denial of service attacks or remote code execution.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2002-12-04</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-01-20</td></tr>
<tr><td class="cve-header">Update 2.0.44 released</td><td class="cve-value">2003-01-20</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.43, 2.0.42?, 2.0.40?, 2.0.39?, 2.0.37?, 2.0.36?, 2.0.35?</td></tr>
</table></dd>
<dt><h3 id="CVE-2003-0017">important: <name name="CVE-2003-0017">Apache can serve unexpected files</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-0017">CVE-2003-0017</a>)</h3></dt>
<dd><p>On Windows platforms Apache could be forced to serve unexpected files by appending illegal characters such as '&lt;' to the request URL</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2002-11-15</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2003-01-20</td></tr>
<tr><td class="cve-header">Update 2.0.44 released</td><td class="cve-value">2003-01-20</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.43, 2.0.42?, 2.0.40?, 2.0.39?, 2.0.37?, 2.0.36?, 2.0.35?</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.43">Fixed in Apache HTTP Server 2.0.43</h1><dl>

<dt><h3 id="CVE-2002-0840">low: <name name="CVE-2002-0840">Error page XSS using wildcard DNS</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2002-0840">CVE-2002-0840</a>)</h3></dt>
<dd><p>Cross-site scripting (XSS) vulnerability in the default error page of Apache 2.0 before 2.0.43, and 1.3.x up to 1.3.26, when UseCanonicalName is "Off" and support for wildcard DNS is present, allows remote attackers to execute script as other web page visitors via the Host: header.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2002-09-20</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2002-10-02</td></tr>
<tr><td class="cve-header">Update 2.0.43 released</td><td class="cve-value">2002-10-03</td></tr>
<tr><td class="cve-header">Update 1.3.27 released</td><td class="cve-value">2002-10-03</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.42, 2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35, 1.3.26, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2, 1.3.1, 1.3.0</td></tr>
</table></dd>
<dt><h3 id="CVE-2002-1156">moderate: <name name="CVE-2002-1156">CGI scripts source revealed using WebDAV</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2002-1156">CVE-2002-1156</a>)</h3></dt>
<dd><p>In Apache 2.0.42 only, for a location where both WebDAV and CGI were enabled, a POST request to a CGI script would reveal the CGI source to a remote user.</p>
<table class="cve"><tr><td class="cve-header">Update 2.0.43 released</td><td class="cve-value">2002-10-03</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.42</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.42">Fixed in Apache HTTP Server 2.0.42</h1><dl>

<dt><h3 id="CVE-2002-1593">moderate: <name name="CVE-2002-1593">mod_dav crash</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2002-1593">CVE-2002-1593</a>)</h3></dt>
<dd><p>A flaw was found in handling of versioning hooks in mod_dav. An attacker could send a carefully crafted request in such a way to cause the child process handling the connection to crash. This issue will only result in a denial of service where a threaded process model is in use.</p>
<table class="cve"><tr><td class="cve-header">Issue public</td><td class="cve-value">2002-09-19</td></tr>
<tr><td class="cve-header">Update 2.0.42 released</td><td class="cve-value">2002-09-24</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.40, 2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.40">Fixed in Apache HTTP Server 2.0.40</h1><dl>

<dt><h3 id="CVE-2002-0654">low: <name name="CVE-2002-0654">Path revealing exposures</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2002-0654">CVE-2002-0654</a>)</h3></dt>
<dd><p>A path-revealing exposure was present in multiview type map negotiation (such as the default error documents) where a module would report the full path of the typemapped .var file when multiple documents or no documents could be served. Additionally a path-revealing exposure in cgi/cgid when Apache fails to invoke a script. The modules would report "couldn't create child process /path-to-script/script.pl" revealing the full path of the script.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2002-07-05</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2002-08-09</td></tr>
<tr><td class="cve-header">Update 2.0.40 released</td><td class="cve-value">2002-08-09</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.39, 2.0.37?, 2.0.36?, 2.0.35?</td></tr>
</table></dd>
<dt><h3 id="CVE-2002-0661">important: <name name="CVE-2002-0661">Path vulnerability</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2002-0661">CVE-2002-0661</a>)</h3></dt>
<dd><p>Certain URIs would bypass security and allow users to invoke or access any file depending on the system configuration. Affects Windows, OS2, Netware and Cygwin platforms only.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2002-08-07</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2002-08-09</td></tr>
<tr><td class="cve-header">Update 2.0.40 released</td><td class="cve-value">2002-08-09</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.39, 2.0.37, 2.0.36, 2.0.35</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.37">Fixed in Apache HTTP Server 2.0.37</h1><dl>

<dt><h3 id="CVE-2002-0392">critical: <name name="CVE-2002-0392">Apache Chunked encoding vulnerability</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2002-0392">CVE-2002-0392</a>)</h3></dt>
<dd><p>Malicious requests can cause various effects ranging from a relatively harmless increase in system resources through to denial of service attacks and in some cases the ability to execute arbitrary remote code.</p>
<table class="cve"><tr><td class="cve-header">Reported to security team</td><td class="cve-value">2002-05-27</td></tr>
<tr><td class="cve-header">Issue public</td><td class="cve-value">2002-06-17</td></tr>
<tr><td class="cve-header">Update 2.0.37 released</td><td class="cve-value">2002-06-18</td></tr>
<tr><td class="cve-header">Update 1.3.26 released</td><td class="cve-value">2002-06-18</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.36, 2.0.35, 1.3.24, 1.3.22, 1.3.20, 1.3.19, 1.3.17, 1.3.14, 1.3.12, 1.3.11, 1.3.9, 1.3.6, 1.3.4, 1.3.3, 1.3.2, 1.3.1, 1.3.0</td></tr>
</table></dd>
</dl></br/>

<h1 id="2.0.36">Fixed in Apache HTTP Server 2.0.36</h1><dl>

<dt><h3 id="CVE-2002-1592">low: <name name="CVE-2002-1592">Warning messages could be displayed to users</name>
(<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2002-1592">CVE-2002-1592</a>)</h3></dt>
<dd><p>In some cases warning messages could get returned to end users in addition to being recorded in the error log. This could reveal the path to a CGI script for example, a minor security exposure.</p>
<table class="cve"><tr><td class="cve-header">Issue public</td><td class="cve-value">2002-04-22</td></tr>
<tr><td class="cve-header">Update 2.0.36 released</td><td class="cve-value">2002-05-08</td></tr>
<tr><td class="cve-header">Affects</td><td class="cve-value">2.0.35</td></tr>
</table></dd>
</dl></br/>