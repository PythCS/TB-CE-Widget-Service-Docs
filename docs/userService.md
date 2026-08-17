# USER SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

**1. getUsers** (!!CE VERSION!!)

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getUsers(pageLink).subscribe(users => {
  console.log('Get Users:', users);
});
```

**2. getTenantAdmins**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getTenantAdmins('your-tenant-id', pageLink).subscribe(admins => {
  console.log('Get Tenant Admins:', admins);
});
```

**3. getCustomerUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getCustomerUsers('your-customer-id', pageLink).subscribe(users => {
  console.log('Get Customer Users:', users);
});
```

**4. getUsersForAssign**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getUsersForAssign('your-alarm-id', pageLink).subscribe(usersForAssign => {
  console.log('Get Users For Assign:', usersForAssign);
});
```

**5. getUser**

```javascript
self.ctx.userService.getUser('your-user-id').subscribe(user => {
  console.log('Get User:', user);
});
```

**6. getUsersByIds**

```javascript
self.ctx.userService.getUsersByIds('your-userids-value').subscribe(usersByIds => {
  console.log('Get Users By Ids:', usersByIds);
});
```

**7. saveUser**

```javascript
self.ctx.userService.saveUser('your-user-value', 'your-email@example.com').subscribe(user => {
  console.log('Save User:', user);
});
```

**8. getActivationLink**

```javascript
self.ctx.userService.getActivationLink('your-user-id').subscribe(activationLink => {
  console.log('Get Activation Link:', activationLink);
});
```

**9. getActivationLinkInfo**

```javascript
self.ctx.userService.getActivationLinkInfo('your-user-id').subscribe(activationLinkInfo => {
  console.log('Get Activation Link Info:', activationLinkInfo);
});
```

**10. setUserCredentialsEnabled**

```javascript
self.ctx.userService.setUserCredentialsEnabled('your-user-id', true).subscribe(userCredentialsEnabled => {
  console.log('Set User Credentials Enabled:', userCredentialsEnabled);
});
```

**11. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.findUsersByQuery(pageLink).subscribe(usersByQuery => {
  console.log('Find Users By Query:', usersByQuery);
});
```
