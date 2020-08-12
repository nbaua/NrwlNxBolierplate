# Execute the following commands

## Install nrwl (nx) cli - Avoid global install on production server (by removing g flag)

    npm install -g @nrwl/cli

### Create NX workspace

    npx create-nx-workspace@latest

### Follow the onscreen commands, (using Nest and Angular)

> ? Workspace name (e.g., org name) nx-boilerplate

> ? What to create in the new workspace angular-nest [a workspace with a full stack application (Angular + Nest)]

> ? Application name web

> ? Default stylesheet format SASS(.scss) [ http://sass-lang.com ]

> ? Use the free tier of the distributed cache provided by Nx Cloud? No [Only use local computation cache]

### Switch to workspace directory

    cd nx-boilerplate

### Optional: Check the current setup

By running the following commands
nx serve api OR ng run api:serve
nx serve web OR ng run web:serve

## Add an additional Angular project

    nx g @nrwl/angular:app admin-console

### Follow the onscreen commands

> ? Which stylesheet format would you like to use? SASS(.scss) [ http://sass-lang.com ]
> ? Would you like to configure routing for this application? Yes

## Additional Steps

Change default port setting for angular projects to avoid conflict with other projects

### Open `angular.json`

locate the `serve` block for the Angular projects and add `port` option as under with the desired port value.

_This setting does not apply to Node API or other project types._

    "serve": {
        "builder": "@angular-devkit/build-angular:dev-server",
        "options": {
        "browserTarget": "web:build",
      + "port": 4201,
        "proxyConfig": "apps/web/proxy.conf.json"
    },

> Notice the new `port` key with custom port number above.
