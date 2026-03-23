Make the script executable and run it in base catalog:

```chmod +x setup.sh```\
```./setup.sh```

Auth0 Setup \
Docs: \
https://auth0.com/docs/quickstart/spa/vuejs \
https://auth0.com/docs/quickstart/backend/laravel/interactive

If you already have existing auth0 app and api - Export Existing Auth0 Configuration (run inside backend catalog)
1. List your existing apps and find the one you want: \
```./auth0 apps list``` 
2. Export your existing app's details to the config file: \
```./auth0 apps show <YOUR_APP_CLIENT_ID> --json --reveal-secrets > .auth0.app.json```
3. List your existing APIs: \
```./auth0 apis list```
4. Export your existing API's details to the config file: \
```./auth0 apis show <YOUR_API_ID> --json > .auth0.api.json```
5. Add the config files to .gitignore: \
```echo ".auth0.*.json" >> .gitignore```

Copy from .env.example to .env in frontend catalog
```
VITE_AUTH0_DOMAIN=
VITE_AUTH0_CLIENT_ID=
VITE_API_URL=
``` 

Start containers: \
```docker compose up --build```

Laravel – First Run (in base catalog) \
```docker compose exec backend composer install``` \
```docker compose exec backend cp .env.example .env``` \
```docker compose exec backend php artisan key:generate```

You can see project under address: http://localhost:5173