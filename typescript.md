[*Go back to the index*](README.md)  

# Index

- [Cookies](#cookies)

# Cookies

In order to use cookies we are going to need an external package called *ngx cookie service*  
[Official documentation page](https://www.npmjs.com/package/ngx-cookie-service)

So to include this package into our angular page we are going to need to execute this command:

```
npm install ngx-cookie-service --save
```
[--save](angular.md/#save)

Now we can add this service to our ```app.module.ts``` as a provider.

**Note**: If you do not have this file because you are in an angular version 18 or above then that's even better, you can just skip this step.

>import {CookieService} from 'ngx-cookie-service';
>
>@NgModule({  
>&nbsp;&nbsp;&nbsp;&nbsp;...  
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;providers:  
>[CookieService],  
>...  
>})  
>  
>export class AppModule {  
>}

Then, import and inject it into a constructor:

>constructor(private  
>cookieService: CookieService  
>)  
>{  
>&nbsp;&nbsp;&nbsp;&nbsp;this.cookieService.set('Test', 'Hello World');  
>&nbsp;&nbsp;&nbsp;&nbsp;this.cookieValue = this.cookieService.get('Test');  
>}

And that's it!

There are a couple more things about this that I'd recommend checking out in the [official documentation](https://www.npmjs.com/package/ngx-cookie-service). They are not required for normal simple use, but are interesting and good to know anyway, and include things for server side rendering and others.

___
[*Go back to the index*](README.md) 