# Login

El proyecto fue generado con [Angular CLI](https://github.com/angular/angular-cli) version 15.0.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.

# Introducción
En éste pequeño ejemplo se creará una aplicación para registro e ingreso de un usuario.

## Primera parte crear la interfaz de usuario de Login.
### 1. Generar el proyecto Angular
~~~
ng new login
~~~
- Es necesario seleccionar un módulo de routing.
- Utilizar el estilo **SCSS**.

### 2. Instalar los módulos
Cambiarse al directorio recien creado en el punto 1 e instalar los módulos default cuando se instalar la aplicación.
~~~
cd login
npm install
~~~

### 3. Agregar los componentes login y registro
Mediante la terminal agregar las instrucciones, vease [Components](https://angular.io/guide/component-overview)
~~~
 ng g c components/login
 ng g c components/register
~~~

![image](https://user-images.githubusercontent.com/8560750/215362677-e296d9ea-87bd-4f24-b361-ccf07c95bf6f.png)

### 4. Definir las rutas de login y registro
La idea inicial es tener tres rutas: ** Home, Login,  y Register**.

Modificar el archivo app-routing.module.ts, sino recuerda el ruteo vea lla siguiente referencia [Routes](https://angular.io/api/router/Route)
~~~
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { AppComponent } from './app.component';
import { LoginComponent } from './components/login/login.component';
import { RegisterComponent } from './components/register/register.component';

const routes: Routes = [
  {path:'', component:AppComponent, pathMatch:'full'},
  {path:'login', component:LoginComponent, pathMatch:'full'},
  {path:'register', component:RegisterComponent, pathMatch: 'full'}
];  

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
~~~

### 5. Agregar el módulo FormsComponent
Abrir y modificar el archivo app.module.ts
- Configuración de los módulos Login y Register recién creados.
- Agregar el módulo FormsModule para el manejo de formularios.

~~~
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';


import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { LoginComponent } from './components/login/login.component';
import { RegisterComponent } from './components/register/register.component';
import { FormsModule } from '@angular/forms';

@NgModule({
  declarations: [
    AppComponent,
    LoginComponent,
    RegisterComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule, 
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
~~~

