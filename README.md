<h1 align="center">
 ngx-material-luxon
</h1>

<br />

[![MIT](https://img.shields.io/packagist/l/doctrine/orm.svg?style=flat-square)]()
[![commitizen](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat-square)]()
[![PRs](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)]()
[![styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)
[![All Contributors](https://img.shields.io/badge/all_contributors-0-orange.svg?style=flat-square)](#contributors-)


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
