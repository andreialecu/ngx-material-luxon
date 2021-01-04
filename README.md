# NgxMaterialLuxon

[Luxon](https://moment.github.io/luxon/) Date Adapters for Angular Material

This is based on the work of [crisbeto](https://github.com/crisbeto) in https://github.com/angular/components/pull/14681. Original PR has been left unmerged due to https://github.com/angular/components/pull/14681#issuecomment-457685311

## Installation

```bash
npm install --save ngx-material-luxon
```

```bash
yarn add ngx-material-luxon
```

## Usage:

```ts
import { MatLuxonDateModule } from 'ngx-material-luxon';
```

Add `MatLuxonDateModule` to your root `@NgModule` `imports`.

## Caveats:

Luxon does not support returning information about the first day of the week. The library provides the ability to override the value used as the first day of the week.

Example:

```ts
const firstDayOfWeek = (locale: string) => { return 1; } // Monday

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

This is left for the user to implement. Ideally it should be supplied via something like [weekstart](https://npmjs.com/package/weekstart)
