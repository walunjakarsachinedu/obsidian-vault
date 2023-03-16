### Routing and Navigation
Angular provide "`RouteModule`" for navigation. 
           
In angular, we add navigation using following steps
- configure the routes
- add a router outlet
- add links
        
#### Configure the Routes
```typescript
// file:app.module.ts
@NgModule({
  imports: [
    { path: '', component: HomeComponent },
    { path: 'home', component: HomeComponent },
	{ path: 'posts', component: PostsComponent },
	{ path: 'post', component: PostComponent },
  ]
})
```
        
#### Add a Router Outlet
component will be displayed after `router-outlet` tag based on current routes.
```html
<!-- file:app.component.html -->
<router-outlet></router-outlet>
```

#### Add Links
- use `routerLink` directive to add link to page. it will only download asset for current page & navigate to that page.           
- don't use `href` attribute, it will redownload javascript bundle and re-initialize angular application every time link is clicked.
- route parameters are passed in list to routerLink where first value is route after which route parameter are passed.
```html
<a routerLink="/posts">Posts</a>
<!-- passing route parameter -->
<a [routerLink]="['/followers', follower.id]">
```
          
`routerLinkActive`: This directive attribute use it to include classes with link is active
e.g, it can be use to highlight active nav element.

#### Single Page Applications 
- single page is download from server and as the user navigate from one page to another page only content of target page is downloaded.
- javascript, css bundle downloaded only first time 
- it is achieved using `routerLink` tag.


### Accessing Route Parameters
This parameter can be access using `ActivatedRoute` dependency provided by angular `RouteModule` 
```typescript
// getting route parameter
router.paramMap.get('parameter-name').subscribe(value => console.log(value));
// getting query parameter
router.queryParamMap.get('parameter-name').subscribe(value => console.log(value));
```

### Important note
Angular not destroy component only if we navigate to same page using different route parameter. Because of which we need to subscribe to value provided by router parameter, so that component will get notify everytime new value arrive.
- This is a reason why router return `Observable` & not `Promise`.