> [!WARNING]
> Incomplete chapter

#### Config and run `frontend` module
Go to `frontend` folder  
1. `$>npm install`  
2. create prod. dist.:  
`$>npm run build`  
3. run server (install `http-server` if necessary):  
`http-server dist/`

5. start mid with live reload pages (instant refresh in browser):  
   `$>DEBUG=mid:* node app.js`
6. Debug frontend:  
   start server in debug mode:  
   `$>node --inspect ./node_modules/@vue/cli-service/bin/vue-cli-service.js serve`
   connect from Intellij idea: create debug/run config:   
   "debug javascript" > insert in url: "ws://127.0.0.1:9229/b727369a-1135-480a-9111-ad90f3c40a52" > run it in debug mode

### Start frontend locally
1. run backend for api to work
2. set env. var `VUE_APP_BACKEND_API_URL` in frontend to backend api
   (e.g. if backend port is 8090: `export VUE_APP_BACKEND_API_URL=http://localhost:8280/api`)

### Integrate frontend prod build to backend:
1. On frontend run:  
   `$>npm run build`
2. copy `dist/*` files to `backend/main/resources/public/*`
3. Run backend: `http://localhost:<port>/index.html`

See also:  
https://devcenter.heroku.com/articles/deploying-executable-jar-files  
https://devcenter.heroku.com/articles/deploying-spring-boot-apps-to-heroku
https://github.com/heroku/heroku-cli-deploy
