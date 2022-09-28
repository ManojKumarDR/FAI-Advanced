# FAI-Advanced
Advanced Training on MVC, Angular and React
# Angular Tutorial
Angular is a JS Framework developed by Google for creating Rich UI-based Apps that run on multiple devices and Platforms. The latest version is 14. Google releases new versions once in 6 months. Most of the features will be enhancement of the App build and execution with little features also added up. Most of the enhancements will be on the optimization of the Code that is generated by Angular.

Angular uses Components to make up the Application. A Component in Angular is a self-contained unit that has all the requirements of a UI that will run on a Browser. HTML + CSS + Logical Code that is created using a Sp language called TypeScript. TS is an MS product, that works like an Enhanced version of JS. It is more typesafe than JS. 

Angular Apps are developed using a Boiler-plate code that is generated using Command line tools provided by Angular.

### Software requirements for Angular:
1. NodeJS installed in UR Machine. Nodejs acts like a web server for the development environment of Angular App.
2. Install the Angular CLI Command Utility using Node Package Manager.   
   ```
     npm install -g @angular/cli
   ```

### Commands for creating Angular App
- ng new app-name ==> Creates a new App with a wizard support in a folder named on the app name. 
- cd app-name ==>Move to the directory of the App
- ng serve --open ==>Builds the App, runs it and opens it in the default browser of the System.

```
ng new app-name
cd app-name
ng serve --open
```

### Features:
1. It is used for creating Single Page Apps. There will be only one Main HTML page called as Index that makes UR App.
2. It uses Components, independent self-contained units that will make up UR Application. UR App will comprise of 100s of components that will be having its own html, css, unittesting code as well as the Logical code behind that contains the event handlers for the html elements.
3. Unit Testing is one of the features of Angular where U can have Unit testing done on each of the functionality of the Angular component. It also supports e2e(End to End) Testing using an Automation testing framework called Protractor. Jasmine is the testing framework for unit testing. 
4. Data Binding is a very popular feature where we can bind the data of the component the User interface represented as HTML Content. Default is one-way binding. The binding happens from TS file to the html file. Using FormsModule, we can achieve 2 way binding also.  
 
### How to create new Component:
```
ng generate component Components/ComponentName
```
To generate Components without Unit Tests Code:
```
ng generate component Components/MyNewFeature --skipTests
```

### Updating tables after modification:
1. Update the table to add a new column for the images in the Code First Approach of EF Core:
- Add a new property to the model class.
- Run the Add-migration tool
- Run the update-database tool.

2. Modify the code in the web API to allow updating the image into the web API.
Modify the Update function by adding a new statement to update the image of the selected employee

3. Consume the Web API in our Angular App by creating a new Component and its data. 
### Services:
Services in Angular are Singleton Classes that are used to share the state of the singleton object across the application and its components. Its scope will be within the module of the service that is created. 
We create services to access external RESTFull Services available on the web. 
Advantages of the services in Angular:
- Helps in maintaining singleton data so that U can use it across the Components. 
- Helps in Dependency Injection. All services in Angular will have a Directive called @Injectable that makes it to be used anywhere, in any component of the module available. 
How to create a service:
```
ng g s Services/Employee --skip-tests=true
```

4. Apply the routing feature to the existing angular app:
### Routing:
- U can create a seperate module and add it into the App.Module. However, U can create it within the App Module itself. 
- U need to define the routes using Routes[] defined in RouterModule. The routes contain the possible Url mappings to the respective Components. U should also add the RouterModule.forRoots(routes) line in the imports section of the module. 
- U should use the <router-outlet> tag for defining the location for loading the components when the route pattern is requested in the Url. 
- Hyperlinks will be set using router-link attribute instead of href. 
```
   const routes : Routes =[
  {path: '', redirectTo: "Home", pathMatch:'full'},
  {path: 'Home', component: HomeComponent},
  {path: 'Employees/All', component: EmpMgrComponent},
  {path: 'Employees/Add', component: AddNewEmpComponent},
  {path: 'Employees/Edit/:id', component: EditEmpComponent},
  {path: 'Employees/View/:id', component: ViewEmpComponent},
  {path: 'Calc', component: CalcComponent},  
  {path: 'Master', component: MasterComponent}  
]
   //Add this in the imports section of the Module
   imports: [
    BrowserModule,
    FormsModule,
    HttpClientModule,
    RouterModule.forRoot(routes)
  ],
   ```
