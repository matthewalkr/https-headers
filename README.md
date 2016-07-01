# https-headers
Best practice HTTP headers for Apache and IIS. These headers enforce HTTPS across all resources, and commit to future maintenance of HTTPS.

* Redirect all requests to HTTPS
* Add Strict-Transport-Security when HTTPS
* X-Content-Type-Options
* X-Frame-Options
* X-XSS-Protection
* Disable directory browsing

## Redirect all requests to HTTPS

Before changing headers:
* Purchase, install, and test a 2048-bit certificate.
* Switch to relative URLs for internal resources.
* Switch to protocol-relative URLs for external resources, for example //code.jquery.com/ .
* Be aware of SEO implications. Google will treat the change as a site move.

## Add Strict-Transport-Security when HTTPS (HSTS)
This header defines a commitment to HTTPS for a specified period of time, meaning the browser will automatically request HTTPS pages regardless of your site settings. Consider only applying this header once you are comfortable with your live HTTPS set up and have bedded it in over several months. The time period is specified in seconds.

Options include:
* includeSubDomains - applies to all present and future subdomains.
* preload - consents to having domain preloaded by browsers https://hstspreload.appspot.com/ . Note that this is effectively a permanent commitment to retain HTTPS. The minimum max-age for this option is 10886400.

## X-Content-Type-Options
This header blocks enforces correct MIME types.

## X-Frame-Options
This header protects against clickjacking, blocking other sites from placing your site in an iframe.

## X-XSS-Protection
This header protects against cross-site scripting.

## Further reading

* [Secure your site with HTTPS, Google Search Console Help] (https://support.google.com/webmasters/answer/6073543)
* [SSL/TLS Deployment Best Practices, Qualys SSL Labs] (https://www.ssllabs.com/downloads/SSL_TLS_Deployment_Best_Practices.pdf)
* [HTTP Strict Transport Security, OWASP] (https://www.owasp.org/index.php/HTTP_Strict_Transport_Security)
