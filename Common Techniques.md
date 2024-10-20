<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="OSINT Techniques: Learn Search Techniques, Email Analysis, and Scanning for Open Source Intelligence.">
    <title>OSINT Techniques</title>
    <style>
        body {
          background-image: url("osin.jpeg");
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        header {

            color: lime;
            padding: 10px 0;
            text-align: center;
        }
        nav {
            text-align: center;
            background-color: #000000	;
            padding: 10px;
        }
        nav a {
            color: lime;
            margin: 0 15px;
            text-decoration: none;
            font-size: 18px;
        }
        section {
            padding: 20px;
            margin: 20px;
            background-color: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h2 {
            color: #000000;
        }
        footer {
            text-align: center;
            padding: 0px;
            background-color: #000000;
            color: white;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        h1, h2, h4, h5, h6 {
            color: #333;
        }
         pre {
            background-color: #f4f4f4;
            padding: 10px;
            border-left: 5px solid #ccc;
            white-space: pre-wrap;
            word-wrap: break-word;
            margin-bottom: 20px;
        }
        code {
            background-color: #eee;
            padding: 2px 4px;
            font-size: 1em;
            color: #d6336c;
        }
        .copy-frame {
            border: 1px solid #ccc;
            padding: 15px;
            background-color: #000000;
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>OSINT Techniques</h1>
    </header>

    <nav>
        <a href="#osint">About OSINT</a>
        <a href="#search-techniques">Search Techniques</a>
        <a href="#email-analysis">Email Analysis</a>
        <a href="#scanning">Scanning</a>
    </nav>

    <section id="osint">
        <h2>Some Information About OSINT</h2>
        <p>Open Source Intelligence (OSINT) refers to the process of collecting and analyzing publicly available information. This data can be obtained from various sources such as the internet, social media platforms, public records, and more. OSINT is widely used in cybersecurity, investigative journalism, and law enforcement for identifying patterns, analyzing trends, and gathering intelligence.</p>
    </section>

    <section id="search-techniques">
        <h2>Search Techniques</h2>
        <p>Search techniques in OSINT are essential to uncover relevant information hidden across the web. By utilizing advanced search engines, Boolean operators, and domain-specific search tools, investigators can find specific data quickly and efficiently.</p>
        <ul>
       
    <h1>GitHub Dorks - Common Credentials</h1>

    <div class="copy-frame">
        <p>These GitHub dorks help in locating common credentials in repositories:</p>
        <pre>
<code>
path:.env
path:.env passwd
path:.env password
path:.env secret
path:*.env api
path:*.env passwd
path:*.env password
path:*.env secret
path:config.* auth
path:config.* password
path:config.* passwd
path:config.* token
path:config.json password
"example.com" password
"example.com" passwd
"example.com" credential
"example.com" creds
path:.git-credentials
</code>
        </pre>
    </div>
<h2>References : </h2>
 <a href="https://github.com/techgaun/github-dorks"><font color="SpringGreen"><h3> more information </h3> </font></a> 

<li> <h1> Google Dorks </h1>
   <h1>Advanced Search Techniques</h1>

    <h3>Retrieve Cached Results</h3>
    <p>To search for the latest cached version of a website, use the <code>cache:</code> operator followed by the URL:</p>
    <div class="copy-frame">
        <pre><code>cache:example.com</code></pre>
    </div>

    <h3>Country and Language</h3>
    <p>If you want to get search results specific to a certain country and language, use the <code>gl</code> and <code>hl</code> parameters:</p>
    <ul>
        <li><code>gl=us</code>: United States</li>
        <li><code>hl=en</code>: English</li>
    </ul>
    <p>Example:</p>
    <div class="copy-frame">
        <pre><code>https://www.google.com/search?q=apple&gl=us&hl=en</code></pre>
    </div>

    <h3>Directory Listing</h3>
    <p>Search for websites that allow directory listing. You can retrieve all files if enabled on the website:</p>
    <div class="copy-frame">
        <pre><code>intext: "Index of /admin"</code></pre>
    </div>
    <div class="copy-frame">
        <pre><code>intext: "Index of /wp-admin"</code></pre>
    </div>
    <div class="copy-frame">
        <pre><code>site:example.com intext: "Index of /admin"</code></pre>
    </div>

    <h3>File Types</h3>
    <p>To specify the type of file you're looking for, such as a PDF, use <code>filetype:</code> followed by the file extension:</p>
    <div class="copy-frame">
        <pre><code>filetype:pdf</code></pre>
    </div>
    <p>Example with a specific query:</p>
    <div class="copy-frame">
        <pre><code>filetype:pdf "email address"</code></pre>
</p>
</li>
            <li><h2> Social Media Searching: Gathering insights from social platforms like Facebook, Twitter, and LinkedIn... .</h2> </li>
        </ul>
    </section>

    <section id="email-analysis">
    
    
    
    
        <h1>Email Analysis Tools</h1>
    
    <h3>Tool:</h3>
    <p>You can use the following tool for analyzing email addresses:</p>
    <ul>
        <li><a href="https://github.com/alpkeskin/mosint" target="_blank">MOSINT - GitHub</a></li>
    </ul>
        <h2>Example command:</h2>
    <div class="copy-frame">
        <pre><code>mosint example@example.com</code></pre>
        <pre><code>open example.xml</code></pre>
        <pre><code>strings example.eml</code></pre>
        <pre><code>dig example.com txt</code></pre>
        <pre><code>dig example.com txt</code></pre>
    </div>

    <h3>Output Example:</h3>
    <div class="copy-frame">
        <pre><code>example.com.  IN  TXT  "v=spf1 include:spf.example.com -all"</code></pre>
        <pre><code>example.com.  IN  TXT  "v=spf1 +ip4:10.0.0.1/24 -all"</code></pre>
        <pre><code>example.com.  IN  TXT  "v=spf1 a:mail.example.com -all"</code></pre>
        <pre><code>example.com.  IN  TXT  "v=spf1 -all"</code></pre>
        <pre><code>example.com.  IN  TXT  "v=spf1 mx -all"</code></pre>
        <pre><code>dig selector._domainkey.example.com txt</code></pre>
    </div>

    <h3>DKIM Output Example:</h3>
    <div class="copy-frame">
        <pre><code>selector._domainkey.example.com  IN  TXT  k=rsa;p=J8eTBu224i086iK</code></pre>
        <pre><code>selector._domainkey.example.com  IN  TXT  "selector._domainkey.example.com. 0  IN  TXT  "v=DKIM1; p=ABC...123;""</code></pre>
    </div>

    <h3>Additional Web Tools:</h3>
    <p>You can also check out these web tools for email analysis:</p>
    <ul>
        <li><a href="https://labs.inquest.net/" target="_blank">InQuest Labs</a></li>
        <li><a href="https://mha.azurewebsites.net/" target="_blank">Message Header Analyzer</a></li>
        <li><a href="https://www.phishtool.com/" target="_blank">PhishTool</a></li>
    </ul>

    </section>

    <section id="scanning">
        <h2> Network Scanning Tools </h2>
        <p>Scanning is a technique used to detect open services, vulnerable ports, and other weaknesses in a system. It's a fundamental step in penetration testing and network defense.</p>
        <ul>
            <li>Port Scanning: Identifying open ports and services using tools like Nmap.</li>
            <li>Vulnerability Scanning: Detecting potential vulnerabilities in a system or network.</li>
            
             <h3>Nmap:</h3>
             
             <p>Nmap command options:</p>
        
        <ul>
            <li><code>-sS</code>: SYN Scan</li>
            <li><code>-sV</code>: Service/Version detection</li>
            <li><code>-sC</code>: Default NSE (script)</li>
            <li><code>-T2</code>: Timing template</li>
            <li><code>-p-</code>: Scan all ports</li>
        </ul>
    <div class="copy-frame">
      
        <p>Example commands:</p>
        <pre><code>sudo nmap -sSVC -p- &lt;target-ip&gt; -T2</code></pre>
        <pre><code>sudo nmap -sSVC -p 1-65535 &lt;target-ip&gt;</code></pre>
        <pre><code>sudo nmap -sSVC -p 1000-1500 &lt;target-ip&gt;</code></pre>
        </div>

        <p>If performing port scans in a CTF (Capture The Flag) or testing environment, use <code>--min-rate</code> to speed up scanning:</p>
    <div class="copy-frame">
        <pre><code>sudo nmap -sSVC -p- &lt;target-ip&gt; --min-rate 1000</code></pre>
    </div>

    <h3>Masscan:</h3>
    <p>Masscan is a TCP port scanner that is faster than Nmap.</p>
            <p>Example commands:</p>
    <div class="copy-frame">
        <pre><code>masscan &lt;target-ip&gt;/16</code></pre>
        <pre><code>masscan &lt;target-ip&gt;/24</code></pre>

</div>
        <p>Scan specific ports:</p>
    <div class="copy-frame">
        <pre><code>masscan &lt;target-ip&gt;/16 -p 80,443</code></pre>
        <pre><code>masscan &lt;target-ip&gt;/16 -p 22-80</code></pre>
        <pre><code>masscan &lt;target-ip&gt;/16 -p 0-65535</code></pre>
        <pre><code>masscan &lt;target-ip&gt;/16 --top-ports 100</code></pre>
    </div>

    <h3>RustScan:</h3>
    <p>RustScan is a modern port scanner that is faster than Nmap.</p>
            <p>Example commands:</p>
    <div class="copy-frame">
        <pre><code>rustscan -a &lt;target-ip&gt; -- -sSVC</code></pre>
        <pre><code>rustscan -a &lt;target-ip&gt; -- -sS -A</code></pre>
    </div>


            <li> <h1> Finish 
            <br>
            <br>
                        "These pieces of information are just a drop in a vast ocean."
            </h1> </li>
            <br>
        </ul>
    </section>
    <footer>
        <p>© 2024 OSINT Techniques | All rights reserved.</p>
    </footer>
</body>
</html>
