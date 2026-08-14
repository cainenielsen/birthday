# 🎉 birthday

A tiny, silly birthday card web page. Send someone a link and they get a
full-screen, randomly-colored "Happy Birthday" with a random goofy quote,
a shaking gift button that pops confetti, and a zig-zag background that
re-randomizes on every visit.

**Live:** https://caineandrebekah-birthday.web.app

## Features

- 🎨 Random color palette applied per-letter, per-visit
- 💬 A random one-liner pulled from a big list of birthday quotes
- 🎊 Confetti burst on tap/click of the gift button (via [canvas-confetti](https://www.kirilv.com/canvas-confetti/))
- ✏️ Optional personalized name — see below
- 📱 Responsive layout for portrait and landscape

## Personalizing the message

The name is just a route param — append it to the URL:

```
https://caineandrebekah-birthday.web.app/Alex
```

renders "Happy Birthday, Alex" instead of the plain default. No query
string, no config — just `/` followed by the name.

## Tech stack

- [Vue 3](https://vuejs.org/) (Vue CLI 4 / `@vue/cli-service`)
- Vue Router (single optional-param route: `/:name?`)
- Vuex (scaffolded, currently unused)
- [canvas-confetti](https://www.kirilv.com/canvas-confetti/)
- Firebase Hosting for deploys

## Project setup

```
npm install
```

### Compile and hot-reload for development

```
npm run serve
```

> **Note:** this project uses Vue CLI 4 / webpack 4, whose toolchain
> predates Node's strict ESM `exports` resolution. If `npm run serve`
> fails with `ERR_PACKAGE_PATH_NOT_EXPORTED`, run it under Node 16
> (e.g. `nvm use 16`) rather than a newer Node release.

### Compile and minify for production

```
npm run build
```

## Deployment

Firebase Hosting deploys are automated via GitHub Actions
(`.github/workflows/`):

- Pushing to `master` deploys to the live channel.
- Opening a PR builds a preview channel deploy.

Project: `caineandrebekah-birthday`. To deploy manually instead:

```
npm run build
firebase deploy --only hosting
```

### Customize configuration

See the [Vue CLI Configuration Reference](https://cli.vuejs.org/config/).
