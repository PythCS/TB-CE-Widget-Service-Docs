# USER SERVICE

Part of [ThingsBoard CE Widget Service Documentation](../DOCUMENTATION.md)

### **USER SERVICE**

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
userService.getUsers(pageLink).subscribe(users => {
  console.log('Get Users: users');
});
```

**2. getTenantAdmins**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getTenantAdmins('your-tenant-id', pageLink).subscribe(tenantadmins => {
  console.log('Get Tenant Admins: tenantadmins');
});
```

**3. getCustomerUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getCustomerUsers('your-customer-id', pageLink).subscribe(customerusers => {
  console.log('Get Customer Users: customerusers');
});
```

**4. getUsersForAssign**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getUsersForAssign('your-alarm-id', pageLink).subscribe(usersForAssign => {
  console.log('Get Users For Assign: usersForAssign');
});
```

**5. getUser**

```javascript
userService.getUser('your-user-id').subscribe(user => {
  console.log('Get User: user');
});
```

**6. getUsersByIds**

```javascript
userService.getUsersByIds('your-id').subscribe(usersbyids => {
  console.log('Get Users By Ids: usersbyids');
});
```

**7. saveUser**

```javascript
const user = user;
userService.saveUser(user, true).subscribe(savedUser => {
  console.log('Save User: savedUser');
});
```

**8. getActivationLink**

```javascript
userService.getActivationLink('your-user-id').subscribe(activationLink => {
  console.log('Get Activation Link: activationLink');
});
```

**9. getActivationLinkInfo**

```javascript
userService.getActivationLinkInfo('your-user-id').subscribe(activationLinkInfo => {
  console.log('Get Activation Link Info: activationLinkInfo');
});
```

**10. setUserCredentialsEnabled**

```javascript
userService.setUserCredentialsEnabled('your-user-id', true).subscribe(result => {
  console.log('Set User Credentials Enabled: result');
});
```

**11. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.findUsersByQuery(pageLink).subscribe(results => {
  console.log('Find Users By Query: results');
});
```
