# goldbelly-gift-card

Notes:

* App init with Vue CLI

* I would have preferred to use a webfontloader plugin for Google Fonts, though I couldn't seem to find one that was compatible with the latest Vue CLI 3.x

* This assumes you have Futura installed locally. In an ideal/production situation, I'd self host Cabin and Futura (with proper licenses) and serve asyncronously them as custom web fonts (`@font-face`)

* Amount input would need better validation in a production environment.


# Vue CLI Setup

```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
