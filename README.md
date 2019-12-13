"# spring-boot-oauth2" 

-Dspring.profiles.active=default,dev

use Cookies convenience methods in xhr:

application-dev.yml
spring:
  profiles:
    active: dev
    include: default
    
Use different annotation @EnableOAuth2Client.
To remove the @EnableOAuth2Sso and replace it with the lower level annotation

#Manual Configuration of OAuth2 Client
@EnableOAuth2Client

convert the application.yml to a slightly new format,
 where the prefix for configuration is facebook instead of security.oauth2: