# docs-oxd
All rights reserved -- Copyright 2015 Gluu Inc.

# oxd

oxd is a mediator, a service demon that listens on localhost, providing easy APIs that can be called by a web application to simplify using an OpenID Connect Provider, like Google or the [Gluu Server](http://gluu.org/docs), for authentication or authorization. oxd is not a proxy--sometimes it makes API calls on behalf of an application, but other times it just forms the right URLs and returns them to the application.

Using oxd to support federation in an application provides both technical and business advantages:

1. oxd consolidates the OAuth2 code in one package. If new vulnerabilities are discovered in OAuth2/OpenID Connect, oxd is the only component that needs to be updated. The oxd APIs remain the same, so you don’t have to change and regression test your applications;       

2. oxd is written, maintained, and supported by developers who specialize in application security. Because of the complexity of the standards–and the liability associated with poor implementations–it makes sense to rely on professionals who have read the specifications in their entirety and understand how to properly implement the protocols;       


3. Centralization reduces costs. By using oxd across your IT infrastructure for application security (as opposed to a handful of homegrown and third party OAuth2 implementations), the surface area for vulnerabilities, issue resolution, and support is significantly reduced. Plus you have someone to call when something goes wrong!       

# Technical Architecture
![image](https://cloud.githubusercontent.com/assets/5271048/21401608/d7a8a926-c769-11e6-94d4-7f2420df730a.png)

# Plugins

Gluu currently publishes oxd plugins, modules, and extensions for the following open source applications (more coming!):      
- [Wordpress](https://oxd.gluu.org/docs/plugin/wordpress/)      
- [Magento](https://oxd.gluu.org/docs/plugin/magento/)       
- [Drupal](https://oxd.gluu.org/docs/plugin/drupal/)       
- [OpenCart](https://oxd.gluu.org/docs/plugin/opencart/)       
- [SuiteCRM](https://oxd.gluu.org/docs/plugin/suitecrm/)       
- [SugarCRM](https://oxd.gluu.org/docs/plugin/sugarcrm/)       
- [Roundcube](https://oxd.gluu.org/docs/plugin/roundcube/)       

For a complete list of oxd plugins, check the [oxd documentation](http://oxd.gluu.org/docs)

# Libraries
oxd client libraries provide simple, flexible, powerful access to the oxd OpenID Connect and UMA authentication and authorization APIs.     
- [Python](https://oxd.gluu.org/docs/libraries/python/index.md)       
- [Java](https://oxd.gluu.org/docs/libraries/java/index.md)       
- [Php](https://oxd.gluu.org/docs/libraries/php/index.md)       
- [Node](https://oxd.gluu.org/docs/libraries/node/index.md)       
- [Ruby](https://oxd.gluu.org/docs/libraries/rube/index.md)       
- [C#](https://oxd.gluu.org/docs/libraries/csharp/index.md)       

For a complete list of libraries, check the [oxd documentation](http://oxd.gluu.org/docs)

# License
oxd is commercial software licensed by Gluu. Learn more on the [oxd website](https://oxd.gluu.org).

# FAQ's
**What is oxd?**       
oxd is a mediator: it provides API's that can be called by a web application that are easier than directly calling the API's of an OpenID Connect Provider (OP) or an UMA Authorization Server (AS).

**Where do I deploy oxd?**    
oxd is deployed on the same server as the web application(s) you want to protect.

**Why should I use oxd?**     
oxd offers a few key improvements over the traditional model of embedding OAuth 2.0 code in your applications:

1. If new vulnerabilities are discovered in OAuth2/OpenID Connect, oxd is the only component that needs to be updated. The oxd APIs remain the same, so you don't have to change and regression test your applications;     

2. oxd is written, maintained, and supported by developers who specialize in application security. Because of the complexity of the standards--and the liability associated with poor implementations--it makes sense to rely on professionals who have read the specifications in their entirety and understand how to properly implement the protocols;     

3. Centralization reduces costs. By using oxd across your IT infrastructure for application security (as opposed to a handful of homegrown and third party OAuth2 client implementations), the surface area for vulnerabilities, issue resolution, and support is significantly reduced. Plus you who have someone to call when something goes wrong!     

**How is oxd licensed?**        
oxd is commercially licensed. Each time you install oxd you will need to use your license. Active installations are billed $0.33 per day (roughly $10 USD per month per active installation). [Get your oxd license today](http://oxd.gluu.org).  

**Which programming languages and frameworks does oxd have libraries for?**        
Currently there are oxd libraries for the following languages and frameworks:    

- Php   
- Java    
- Python    
- Ruby    
- C#     
- Node.js    
- Spring    
- Lua     

**How do I get SSO across several websites?**                
You’ll need two things:     

1. A central OpenID Connect Provider that holds the passwords and user information;     

2. Websites that use the OpenID Connect protocol to authenticate users.     

An easy way to accomplish the first--utilize [Google as your OP](https://oxd.gluu.org/docs/conf/#using-google-as-an-openid-provider), or install and configure the [free open source Gluu Server](http://gluu.org/docs/deployment) using the Linux packages for CentOS, Ubuntu, Debian or Red Hat. 

The second is accomplished by [installing the oxd service](https://oxd.gluu.org/docs/oxdserver/install/) on each web server that needs SSO. This provides easy to use local API’s that can be called by your web applications, and enables you to use a number of plugins for popular open source software packages.

**Can I use oxd plugins for social login?**    
Currently the Gluu Server supports Google authentication. In the next release (3.0), Gluu will support a new social login module called [Passportjs](http://passportjs.org). This will enable you to use over 300 social login sites, including Facebook or Twitter. Stay tuned!

**Can I use oxd plugins for two-factor authentication (2FA)?**    
You can specify a value for `acr`, which provides the OpenID Connect provider with a hint about what kind of authentication to use. The Gluu Server ships with several built in two-factor authentication mechanisms. Two that are very easy to use are FIDO U2F tokens (like Yubikey) and Duo Security. Gluu also has published a free mobile two factor authentication app for iOS and Android called Super Gluu. If you’re a geek, you can write your own custom authentication script in the Gluu Server, and implement support for any kind of strong authentication technology.

**Can I use Google or Microsoft Azure Active Directory as my OpenID Connect Provider?**    
Probably, but Google and Microsoft do not support dynamic client registration. If you are successful with this, please let us know! It should work.

**Can I purchase support for the Gluu Server or oxd?**    
Yes, for information on paid support, [visit our website](http://gluu.org/pricing).

