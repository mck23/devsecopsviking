# beabetterviking

Vue 2 front end for the **beabetterviking** events site.

## Requirements

- **Node 16.** The current build tooling (Vue CLI 4 / webpack 4) does not run
  on Node 17 or later. With [nvm](https://github.com/nvm-sh/nvm) installed,
  `nvm use` picks up the version from `.nvmrc`.
- **`auth_config.json`** in the repository root (gitignored). For local work on
  the public pages, placeholder values are sufficient.

  Pages behind the Auth0 login require real tenant values and a tenant
  configured to allow `http://localhost:8080` as a callback URL.

## Project setup
```
nvm use
npm ci
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
