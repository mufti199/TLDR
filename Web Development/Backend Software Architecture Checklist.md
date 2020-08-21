[Backend Software Architecture Checklist: How to Build a Product from Scratch](https://www.freecodecamp.org/news/have-an-idea-want-to-build-a-product-from-scratch-heres-a-checklist-of-things-you-should-go-through-in-your-backend-software-architecture/)

1. Implement authentication and authorisation microservices
   - API Keys
   - build applications that don’t need to access more than a single user’s data
   - OAuth
   - enable users to easily provide authorization to applications without needing to share private data or dig through developer documentation
   - JWT
   - with OAuth if you want to limit database lookups and you don’t require the ability to immediately revoke access.
   - It is made of 3 things: header, payload (iss, exp, sub, etc.), and signature
2. Create an abstract base model to be inherited by every other model in your database
   - Follow DRY (don't repeat yourself) religiously
   - There will be certain properties (data) that every table of a database will have, such as
     id, createdAt, updatedAt, deletedAt + isDeleted, uuid, and more. So its better to group them together into a model (or table) of their own
3. Set up a notification microservice
   - Abstraction of nitification microservice from other services such as Authentication and Application (Business Logic) is very important
   - Build 3 functionalities:
     1. Push Notifications (APNS + FCM),
     2. Emails (just integrate an SMTP client for starting
     3. SMS - Have two channels for sending SMS, transactional and promotional (or get sued)
4. Set up error logging
   - Use a middleware to log errors
   - Set up a webHook to be alerted of errors
   - Some third party options could be Airbrake or Sentry.
5. Implement request - response and application logging
   - Comprehensive logs to tract a requests journey are very useful
   - An async system in place that will pick out such request-response and application logs from your system and dump them in a central place. ELK stack is a good option
   - Do Not Log: Passwords, tokens, and OTPs
6. Introduce throttling in your APIs and rate limiting on your application servers
   - This is to prevent Changing IP Brute Force and DDOS attacks
7. Establish and configure asynchronous communication from day one
   - Do not keep the client busy or waiting for backend tasks that can be done asynchronously
8. Set up cron jobs
   - Should not put the cron jobs directly in the crontab file of the server. The framework should handle it as only a DevOps engineer should be allowed access
9. Manage your secrets properly (parameters file)
10. Version your APIs from day one
11. Decide on hard and soft update version checks for your front end clients
    - **Hard updates** refer to when the user is forced to update the client version to a higher version number than what is installed on their mobile.
    - **Soft updates** refer to when the user is shown a prompt that a new version is available and they can update their app to the new version if they want to.
12. Introduce CI/CD from day one
13. Enable Docker support (personal preference)
14. Use an Application Monitoring (APM) tool
15. Use ElasticSearch (or similar) to power application-wide searches in your client apps
    - Traditional databases are not meant for such performant queries
    - When it is time to migrate the search feature to ElasticSearch and introduce a data pipeline into the system.
16. Put a firewall in your production server
    - Close all the ports except the ones to be used for APIs
    - Route the API endpoints using a reverse proxy web server, like NGiNX or Apache
