# USER SERVICE

Part of the [ThingsBoard CE Widget Services Documentation](../DOCUMENTATION.md).

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

**1. getTenantAdmins**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getTenantAdmins('your-tenant-id', pageLink).subscribe(admins => {
  console.log('Get Tenant Admins:', admins);
});
```

**2. getCustomerUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getCustomerUsers('your-customer-id', pageLink).subscribe(users => {
  console.log('Get Customer Users:', users);
});
```

**3. getAllCustomerUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getAllCustomerUsers(pageLink).subscribe(allCustomerUsers => {
  console.log('Get All Customer Users:', allCustomerUsers);
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

**6. getUserInfo**

```javascript
self.ctx.userService.getUserInfo('your-user-id').subscribe(info => {
  console.log('Get User Info:', info);
});
```

**7. getUsers** (!!CE VERSION!!)

```javascript
self.ctx.userService.getUsers('your-userids-value').subscribe(users => {
  console.log('Get Users:', users);
});
```

**8. getUserUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getUserUsers(pageLink).subscribe(userUsers => {
  console.log('Get User Users:', userUsers);
});
```

**9. getAllUserInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getAllUserInfos(true, pageLink).subscribe(allUserInfos => {
  console.log('Get All User Infos:', allUserInfos);
});
```

**10. getCustomerUserInfos**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.getCustomerUserInfos(true, 'your-customer-id', pageLink).subscribe(customerUserInfos => {
  console.log('Get Customer User Infos:', customerUserInfos);
});
```

**11. saveUser**

```javascript
self.ctx.userService.saveUser('your-user-value', 'your-email@example.com', 'your-entitygroupids-value').subscribe(user => {
  console.log('Save User:', user);
});
```

**12. getActivationLink**

```javascript
self.ctx.userService.getActivationLink('your-user-id').subscribe(activationLink => {
  console.log('Get Activation Link:', activationLink);
});
```

**13. getActivationLinkInfo**

```javascript
self.ctx.userService.getActivationLinkInfo('your-user-id').subscribe(activationLinkInfo => {
  console.log('Get Activation Link Info:', activationLinkInfo);
});
```

**14. setUserCredentialsEnabled**

```javascript
self.ctx.userService.setUserCredentialsEnabled('your-user-id', true).subscribe(userCredentialsEnabled => {
  console.log('Set User Credentials Enabled:', userCredentialsEnabled);
});
```

**15. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
self.ctx.userService.findUsersByQuery(pageLink).subscribe(usersByQuery => {
  console.log('Find Users By Query:', usersByQuery);
});
```
