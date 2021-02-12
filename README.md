# Angular

1. npm install -g @angular/cli@7.1.2
2. New project
    ng new ng-fundamentals
3. package.json and angular.json files are used for configuring number of settings for our project that CLI will be using 
4. In src/app you'll do most of your coding
5. In asset folder you put static assets like images, css etc
6. go to ng-fundamentals folder and do npm start
7. Component is consists of 3 files, CLI creates app component
  1.Componet : app.component.ts
  2.Its template : app.component.html
  3.Its styles : app.component.css
  
8. Bootstrap of our app begins with main.ts file and in angular.js file main property points to that main.ts file ("main": "src/test.ts")
9. In main.ts file we are bootstrapping our app using AppModule --> platformBrowserDynamic().bootstrapModule(AppModule) 
10. Angular applications are grouped into modules and every angular application has AppModule, that module is defined as app.module.ts and you can in that file that AppModule is bootstrapped with AppComponent (bootstrap: [AppComponent])
11. index.html file is loaded in our browser and and it loads our app.component
12. Webpack needs to know which files to bundle up when it builds the app. You cant cant statically access any file that is relative to index.html you'll have to setup a path in angular.json 
    e.g "assets": [
              "src/favicon.ico",
              "src/assets"
            ],
            That's why we were able to do this in app.componets.ts file adding image from assets folder
            @Component({
              selector: 'app-root',
              template: `
                <h2>Hello world<h2>
                <img src="/assets/images/basic-shield.png"/>
              `,
              styleUrls: ['./app.component.css']
            })
  
13.
    
  
