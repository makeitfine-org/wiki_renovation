### build and run project

#### Build and run all tests  
Before run make sure:  
- JAVA_HOME env. var is jdk-21
- nodejs is 16.14.0
- npm is 8.3.1  
   `$> gradle buildAll`

> [!Tip]
> It's might be useful for avoiding conflicts to stop and remove
> other docker containers before execution `buildAll` 

#### Run project in docker (todo: separate in other chapter)
   1. `$> docker compose up`  
   * To run in debug mode:  
   `$> docker compose -f docker-compose.yml -f docker-compose-debug.yml up`   
   2. run (if needed in `debug` mode) apps:
      # - InfoApplication.kt  
      - RenovationApplication.kt  
      (with env. vars: INFO_SERVICE_URL=http://localhost:9190/graphql)
   3. open application in browser url: http://localhost:8280    

> [!Tip]
> use username/password to login: `all-test/test` 
> also credentials can be seen it in file: `application-secured-test.yml` 
