### run and usage project

#### Build and run all tests  
   `$> gradle buildAll`

> [!Tip]
> It's might be useful for avoiding conflicts to stop and remove
> other docker containers before execution `buildAll` 

#### Run project in docker 
   1. `$> docker compose up`  
   * To run in debug mode:  
   `$> docker compose -f docker-compose.yml -f docker-compose-debug.yml up`   
   2. run (if needed in `debug` mode) RenovationApplication.kt  
   3. open application in browser url: http://localhost:8280    

> [!Tip]
> use username/password to login: `all-test/test` 
> also credentials can be seen it in file: `application-secured-test.yml` 
