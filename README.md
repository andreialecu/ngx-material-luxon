<h1 align="center">

 ngx-material-luxon
</h1>

<br />

![npm](https://img.shields.io/npm/v/ngx-material-luxon?style=flat-square)
[![Downloads](https://img.shields.io/npm/dm/ngx-material-luxon?style=flat-square)]()
[![MIT](https://img.shields.io/packagist/l/doctrine/orm.svg?style=flat-square)]()
[![commitizen](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat-square)]()
[![PRs](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)]()
[![styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-2-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->


> Luxon Date Adapter for Angular Material

Credits for most of this go to [crisbeto](https://github.com/crisbeto) in https://github.com/angular/components/pull/14681. 

Original PR has been left unmerged due to https://github.com/angular/components/pull/14681#issuecomment-457685311


## Features

- ✅ Drop an import in your `@NgModule` and enjoy Luxon `DateTime` objects

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [FAQ](#faq)

## Installation

### NPM

`npm install ngx-material-luxon --save`

### Yarn

`yarn add ngx-material-luxon`

## Usage


```ts
import { MatLuxonDateModule } from 'ngx-material-luxon';

@NgModule({
  imports: [MatLuxonDateModule]
})
class AppModule { }
```

## FAQ

### Specifying the first day of the week

Luxon does not support have built-in support for returning the first day of the week of the current locale. However, the library allows overriding it via an optional hook.

Example:

```ts
const firstDayOfWeek = (locale: string) => {
  // 0 = Sunday, 1 = Monday, etc
  return 1;
}

@NgModule({
  imports: [LuxonDateModule],
  providers: [
    {
      provide: MAT_LUXON_DATE_ADAPTER_OPTIONS,
      useValue: { firstDayOfWeek },
    },
  ],
})
```

For most apps, a simple return like above is probably fine. For more complex apps, you can use a third party library like: [weekstart](https://npmjs.com/package/weekstart)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/andreialecu"><img src="https://avatars0.githubusercontent.com/u/697707?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Andrei Alecu</b></sub></a><br /><a href="https://github.com/andreialecu/ngx-material-luxon/commits?author=andreialecu" title="Documentation">📖</a> <a href="#infra-andreialecu" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a> <a href="https://github.com/andreialecu/ngx-material-luxon/commits?author=andreialecu" title="Code">💻</a> <a href="#projectManagement-andreialecu" title="Project Management">📆</a></td>
    <td align="center"><a href="https://harves.net/"><img src="https://avatars3.githubusercontent.com/u/12858056?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Daniel Harvey</b></sub></a><br /><a href="https://github.com/andreialecu/ngx-material-luxon/issues?q=author%3Adanielsharvey" title="Bug reports">🐛</a> <a href="https://github.com/andreialecu/ngx-material-luxon/commits?author=danielsharvey" title="Code">💻</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
