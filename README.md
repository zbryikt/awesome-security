# Awesome-security

Checklist for security in web applications.

## checklist

 * CSRF protection for all APIs not intended to be accessed from out of the same origin
 * Prevent referer been set for credential URL
 * Enable X-Frame-Options for all pages not intended to be iframed
 * Headers
   - https://medium.com/@Johne_Jacob/7-security-response-headers-every-security-tester-should-know-77576ffdfc0f
   - https://www.keycdn.com/blog/http-security-headers
   - https://www.upguard.com/blog/infrastructure-indexing-or-why-server-headers-matter-more-than-ever
 * General
   - https://www.upguard.com/blog/the-website-security-checklist

## Throttling
 * Related Modules: https://www.npmtrends.com/express-rate-limit-vs-rate-limit-redis-vs-ratelimit.js-vs-ratelimiter-vs-rolling-rate-limiter
 * https://github.com/nfriedly/express-rate-limit/issues
 * sample ( but not suggest to use express-limiter )
   https://www.codershood.info/2018/06/16/creating-api-rate-limiter-in-nodejs-using-express-and-redis/ )

## Headers
 * ETag - might leak inode information. Nginx should be find though.
 * Strict-Transport-Security - auto use https.
   - if we redirect all http then it will be find?
 * x-powered-by - https://stackoverflow.com/questions/33580671/what-does-x-powered-by-mean
   - set by various servers to say what kind of server it is. disable through ( express ): 
     app.disable("x-powered-by");

## Nginx
 * Security configuration tips - https://medium.com/@nbeguier/nginx-security-configuration-tips-557c35e0d75b


## Express
 * toobusy - 503 to users where your server is too busy - https://github.com/lloyd/node-toobusy


## Cookie
 * HttpOnly - https://www.owasp.org/index.php/HttpOnly
   HttpOnly enforce that cookie cannot be accessed through client side script.

## CSRF - Cross Site Request Forgery
 * Why Doesn't the Django CSRF Cookie Default to 'httponly'?
   https://blog.philipjohnjames.com/django-csrf-httponly/
   - in short - if you need protection in ajax call, then it doesn't matter if you send CSRF Token in cookie without HttpOnly, since the token must be available for your own ajax call in someway that XSS attack can also reach.
