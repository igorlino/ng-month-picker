# ng-month-picker

`ng-month-picker` is a simple month picker for angular application.

## Features
* Simple layout
* Enable/disable form control
* Can be used as an angular form control
* Customize functionality

## Installation

* `npm install ng-month-picker --save`

## Usage

* `import { NgMonthPickerModule } from 'ng-month-picker';`

* add `NgMonthPickerModule` to the imports of your NgModule

```ts
// app.module.ts
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { NgMonthPickerModule } from 'ng-month-picker';
import { AppComponent } from './app.component';
import { FormsModule } from '@angular/forms';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    FormsModule,
    NgMonthPickerModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

And you are good to go...

Use it in your anywhere in your application

````
<ng-month-picker [(ngModel)]="currentMonth"></ng-month-picker>
````

Example for template-driven form:

````
// your.component.html
<form (ngSubmit)="onSubmit()" #infoForm="ngForm">
   <input type="text"  name="title" [(ngModel)]="title">
   <ng-month-picker name="month" [(ngModel)]="currentMonth"></ng-month-picker>
   <button type="submit">Submit</button>
</form>
````

Example for reactive form:

````
// your.component.ts
import { FormControl } from '@angular/forms';
export class YourComponent {
  infoForm = new FormGroup({
      title: new FormControl(''),
      currentMonth: new FormControl(null),
    });
}

// your.component.html
<form [formGroup]="infoForm" (ngSubmit)="onSubmit()">
   <input type="text"  name="title" [formControl]="title">
   <ng-month-picker name="month" [formControl]="currentMonth"></ng-month-picker>
   <button type="submit">Submit</button>
</form>
````
