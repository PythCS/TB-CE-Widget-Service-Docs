# UserService

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('UserService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

**1. getUsers**

```javascript
userService.getUsers(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  Users users:', users);
});
```

**2. getTenantAdmins**

```javascript
userService.getTenantAdmins('your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(tenant => {
  console.log('Fetched  Tenant Admins tenant:', tenant);
});
```

**3. getCustomerUsers**

```javascript
userService.getCustomerUsers('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  Customer Users users:', users);
});
```

**4. getUsersForAssign**

```javascript
userService.getUsersForAssign('your-alarm-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('Fetched  Users For Assign users:', users);
});
```

**5. getUser**

```javascript
userService.getUser('your-user-id').subscribe(users => {
  console.log('Fetched  User users:', users);
});
```

**6. getUsersByIds**

```javascript
userService.getUsersByIds('your-userids-value').subscribe(users => {
  console.log('Fetched  Users By Ids users:', users);
});
```

**7. saveUser**

```javascript
userService.saveUser('your-user-value', 'your-email@example.com').subscribe(users => {
  console.log('Saved  User users:', users);
});
```

**8. getActivationLink**

```javascript
userService.getActivationLink('your-user-id').subscribe(result => {
  console.log('Fetched  Activation Link result:', result);
});
```

**9. getActivationLinkInfo**

```javascript
userService.getActivationLinkInfo('your-user-id').subscribe(info => {
  console.log('Fetched  Activation Link Info info:', info);
});
```

**10. setUserCredentialsEnabled**

```javascript
userService.setUserCredentialsEnabled('your-user-id', true).subscribe(users => {
  console.log('set User Credentials Enabled users:', users);
});
```

**11. findUsersByQuery**

```javascript
userService.findUsersByQuery(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder')).subscribe(users => {
  console.log('find Users By Query users:', users);
});
```
