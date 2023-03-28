### Authentication and Authorization

#### Authenticating user:
User is authenticated if a non-expired JWT token is stored in the browser. To logout, we simply delete the JWT token.
To authenticate user in angular, we use credential to get JWT token and store it in browser.


#### Protecting Routes:
To protect routes, we specify route guards in `canActivate` field while specifying routes. We can specify multiple route guards in an array in the `canActivate` field.

#### Creating route guard:
Navigation is only allowed if all route guards for a route return `true`. 
We create route guard as a service which implement canActivate function of type `CanActivateFn`. e.g., auth guard for admin user:
```typescript
@Injectable({
  providedIn: "root"
})
export class AdminAuthGuard{
  constructor( 
	private router: Router,
    private authService: AuthService
  ) { }

  canActivate: CanActivateFn = (route, state) => {
    if(this.authService.currentUser.admin) return true;
    this.router.navigate(['no-access']);
    return false; 
  }
}
```

#### Showing/hiding content based on the user:
We can use the user data stored in the JWT to show and hide content in our Angular app. We can do this using the `*ngIf` directive in our HTML templates.

#### Protecting routes based on user role:
We can create route guards for specific user roles and apply them to routes that are only accessible by users with that role.


>note: To set the default home page based on the current status of the user, use the `ngOnInit()` method of a component to check the user's status and navigate to a different page if necessary.