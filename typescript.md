[*Go back to the index*](README.md)  

# Index

- [Cookies](#cookies)
- [Angular specific](#angular-specific)
    - [Different CSS files in one project](#different-css-files-in-one-project)

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

# Angular specific

## Different CSS files in one project

Example:

**device-detection.service.ts**

```
export class DeviceDetectionService {
  device?: string;

  constructor() { }
  
  // This (deviceDetection & loadStylesheet) gets executed on the beginning of the creation of the website in "app.component.ts"

  // Detects the device and sets the variable to mobile or desktop
  deviceDetection(){
    const userAgent = navigator.userAgent.toLowerCase();

    if (/mobile/i.test(userAgent)) {
      this.device = "mobile";
      document.body.setAttribute('device', 'mobile');
      // alert ("mobile");
    } else {
      this.device = "desktop";
      document.body.setAttribute('device', 'desktop');
      // alert ("desktop");
    }
  }

  // After knowing on what device the user is loged in with, we give the head of the html document the corresponding css document
  loadStylesheet() {
    const head = document.getElementsByTagName('head')[0];

    // *Create* a new <link> element for the head of the document and *save* it in the variable "linkElement"
    const linkElement = document.createElement('link');
    linkElement.rel = 'stylesheet';
    linkElement.type = 'text/css';
    linkElement.href = this.device === 'mobile' 
      ? 'mobile.css' 
      : 'desktop.css';

    // Add the link element to the head
    head.appendChild(linkElement);
  }
}

```

**app.component.ts**

```
export class AppComponent {

  constructor(
    private deviceDetectionService: DeviceDetectionService,
  ) {
    this.deviceDetectionService.deviceDetection();
    this.deviceDetectionService.loadStylesheet();
  }
}
```

___
[*Go back to the index*](README.md) 