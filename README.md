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