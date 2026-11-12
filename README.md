# Spring_Security_OAuth2
Implementation of OAuth2 as part of advanced Spring Security.

In pom.xml -> sprng-security dependency is not required to add separately for OAuth2.

OAuth provides the facility, to allow login into authorized ages,
without the users to provide username-passord like Basic Authentication.
It provides icon symbols  for other apps like Google or Github, where the credentials
of those platforms are considered as valid for the authorization into the running Project.

For this testing, we need some extra efforts like:

make account in google cloud console and get client id and secret and paste here
# Go to API and Services > Credentials > Create Credentials > OAuth client ID > Web application
# It will ask for redirect URI, add this URI - http://localhost:<server.port>/login/oauth2/code/google or anywhere if we have url SPECIFICALLY
# It will give you client id and secret, like the following.

# Google( in application.properties)
spring.security.oauth2.client.registration.google.client-id=<This is a placeholder for your Google client ID>
spring.security.oauth2.client.registration.google.client-secret=<This is a placeholder for your Google client secret>

# Login to Github and go to settings > Developer settings > OAuth Apps > New OAuth App
# It will ask Homepage URL, add this URL - http://localhost:<server.port>
# It will ask for redirect URI, add this URI - http://localhost:<server.port>/login/oauth2/code/github
# It will give you client id and secret.
# If client secret is not visible, click on Generate a new client secret and copy it.


# Github( in application.properties)
spring.security.oauth2.client.registration.github.client-id=<This is a placeholder for your Github client ID>
spring.security.oauth2.client.registration.github.client-secret=<This is a placeholder for your Github client secret>


# API Endpoints

Method	Endpoint	Description
GET	/	Application home
GET	/login	Initiate login
GET	/oauth2/authorization/google	Start Google OAuth login
GET	/api/user	Get authenticated user
GET	/api/protected	Access protected resource
