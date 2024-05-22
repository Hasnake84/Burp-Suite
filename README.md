<a href="https://imgur.com/84MzfuJ"><img src="https://i.imgur.com//84MzfuJ.png" title="source: imgur.com" /></a>
# Burp-Suite by PortSwigger

# Web application security testing using Burp Suite proxy intercept
In this project, we'll explore how Burp Suite's Proxy Intercept empowers us to test the security of an e-commerce website.
- Capture website traffic using Burp Suite as a proxy.
- Analyze intercepted requests and responses for vulnerabilities like:
- Modify captured requests to test the application's behavior under unexpected conditions.
By leveraging Burp Suite's Proxy Interceptor, we can proactively identify and address security vulnerabilities.
For this lab, we'll need to set two things: the proxy and a Certificate Authority (CA) certificate on our web browser then ensure Burp Suite is running with localhost as the proxy listener. In Firefox settings, set the proxy to point to localhost and its port 8080. We also need to install the Burp Suite CA certificate, which can be found within Burp's options. Finally, create a free account on Portswigger Web Security Academy to access the lab "Lab Logic Flaws - Excessive Trust in Client-Side Controls". Within the lab environment, we should find a shopping webpage accessible through the configured proxy.

# Steps
- Download burpsuite community edition from https://portswigger.net/burp/communitydownload

  <a href="https://imgur.com/eehnStv"><img src="https://i.imgur.com//eehnStv.png" title="source: imgur.com" /></a>   

- Burp Suite > Proxy > Proxy Settings >  Make sure localhost is set to 127.0.0.1:8080 and running
  
  <a href="https://imgur.com/T07WRTe>"><img src="https://i.imgur.com//T07WRTe.png" title="source: imgur.com" /></a>
  
- Firfox web browser > Settings > Network settings > Select > Manual Proxy configuration > localhost port 8080 > check box "Also use this proxy for HTTPS" 

  <a href="https://imgur.com/HTyL9b4"><img src="https://i.imgur.com//HTyL9b4.png" title="source: imgur.com" /></a>

- Go to http://burpsuite > Download the Certificate Authority for Burp suite to create and sign a TLS certificate  

  <a href="https://imgur.com/qGsVfpr"><img src="https://i.imgur.com//qGsVfpr.png" title="source: imgur.com" /></a>

- Firfox web browser > Settings > Privacy/Security > View Certificates > Authorities > Import > Select the CA from Burpsuite > Ok > Restart browser

  <a href="https://imgur.com/vcOxd1F"><img src="https://i.imgur.com//vcOxd1F.png" title="source: imgur.com" /></a>  

- Go to https://portswigger.net > Create acccount > Open email to activate account > Enter name > Retrive Password > 

- Go to https://portswigger.net/web-security/logic-flaws/examples/lab-logic-flaws-excessive-trust-in-client-side-controls > Access Lab

- Click My Account > Enter "wiener" and "peter" for Username and Password respectively > click 'Home' button  

  <a href="https://imgur.com/iXeyBME"><img src="https://i.imgur.com//iXeyBME.png" title="source: imgur.com" /></a>

- From the Home page we select the first item "Leather Jacket" (priced at $1,337.00) click View details
  
- On Burp Suite we now turn on Intercept 

  <a href="https://imgur.com/RDX7Lsu"><img src="https://i.imgur.com//RDX7Lsu.png" title="source: imgur.com" /></a>

-  Home page > View details > Add to cart
-  Now the request will take place and intercepted at the Burp Suite Proxy 
  
  <a href="https://imgur.com/UkCPGNm"><img src="https://i.imgur.com//UkCPGNm.png" title="source: imgur.com" /></a>

- Then we modify the selling price to only $ 0.13  

  <a href="https://imgur.com/HVraXGf"><img src="https://i.imgur.com//HVraXGf.png" title="source: imgur.com" /></a>

- Burp Suite > Proxy > Intercept > Forward
- We go back to webpage and view our shopping cart
- As we can see total balance for check out is modified

   <a href="https://imgur.com/YWgYOq1"><img src="https://i.imgur.com//YWgYOq1.png" title="source: imgur.com" /></a>

Burp Suite has more security testing capabilities, which we will explore and add to this project soon.
