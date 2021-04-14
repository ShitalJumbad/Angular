## Angular

npm install -g @angular/cli@7.1.2

New project ng new ng-fundamentals

package.json and angular.json files are used for configuring number of settings for our project that CLI will be using

In src/app you'll do most of your coding

In asset folder you put static assets like images, css etc

go to ng-fundamentals folder and do npm start

Component is consists of 3 files, CLI creates app component 1.Componet : app.component.ts 2.Its template : app.component.html 3.Its styles : app.component.css

Bootstrap of our app begins with main.ts file and in angular.js file main property points to that main.ts file ("main": "src/test.ts")

In main.ts file we are bootstrapping our app using AppModule --> platformBrowserDynamic().bootstrapModule(AppModule)

Angular applications are grouped into modules and every angular application has AppModule, that module is defined as app.module.ts and you can in that file that AppModule is bootstrapped with AppComponent (bootstrap: [AppComponent])

index.html file is loaded in our browser and and it loads our app.component

Webpack needs to know which files to bundle up when it builds the app. You cant cant statically access any file that is relative to index.html you'll have to setup a path in angular.json e.g "assets": [ "src/favicon.ico", "src/assets" ], That's why we were able to do this in app.componets.ts file adding image from assets folder @Component({ selector: 'app-root', template: <h2>Hello world</h2> <img src="/assets/images/basic-shield.png"/>, styleUrls: ['./app.component.css'] })

Services allow you to define business logic in a seperate file and then inject whaterver service we need whenver we need it

Injectable decorator is required when you inject a service (injecting a service means you have constructor that injects a service)

To let our appp know trhat this service exists we need to register it n or app.module (add it as a provider)

It's really not a good idea to put potentially long running things in our constructor

Compoonents have lifecycle hooks that you can hook into e.g ngOnInitmethod()

Routing In the traditional websites before the advent of single page apps, each page was completely seprate and distinct from others. And every page was served independtly from the server. When you went to index.html, the browser would ask the server for the index.html file. Which the server would then return to the browser and then display. And then if you go foo.html. It would ask server for that file and then file would returnrd and then displayed. Enire page will be replaced even the 60% of the page was the same as the prior page.

Modern web applications however load an app into the memory by loading just a single page, typically index.html, and all other pages are loaded by javascript but they are not really full pages. YOur intial index.html is the only full page load. And then only portions are replaced as you nevigate from page to page around the site. To the user it seeems like new page is being loaded they even see the URL changing in their browser and the back and forward buttons even work despite the fact that only one index,html page has ever actually been loaded from the server. There a lot that goes into making this work, but frameworks like angular have abstracted a lot of that away and made it very simple.

Observable Observables are like are streams of data.They are kind of like arrays where data arrives over time. e.g Subject is observable setTimeout( () => { subject.next(EVENTS); // here we are adding data to our observable stream, we are doing it inside of setTimeout to simulate asynchrony subject.complete(); }, 100 // after 100 ms we will add data to the stream )

this.eventService.getEvents().subscribe( events => { this.events = events}) //this will get set only when data is received. Which happens inside our subscription

You can add new feature module to your application and lazily load them
