# USER SERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

**1. getTenantAdmins**

```javascript
const userService = self.ctx.userService;
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getTenantAdmins(tenantId, pageLink).subscribe(tenantAdmins => {
  console.log('List of Tenant Admins:', tenantAdmins);
});
```

**2. getCustomerUsers**

```javascript
const userService = self.ctx.userService;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getCustomerUsers(customerId, pageLink).subscribe(customerUsers => {
  console.log('List of Customer Users:', customerUsers);
});
```

**3. getAllCustomerUsers**

```javascript
const userService = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getAllCustomerUsers(pageLink).subscribe(allCustomerUsers => {
  console.log('List of All Customer Users:', allCustomerUsers);
});
```

**4. getUsersForAssign**

```javascript
const userService = self.ctx.userService;
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getUsersForAssign(alarmId, pageLink).subscribe(usersForAssigns => {
  console.log('List of Users For Assigns:', usersForAssigns);
});
```

**5. getUser**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
userService.getUser(userId).subscribe(user => {
  console.log('Get User:', user);
});
```

**6. getUserInfo**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
userService.getUserInfo(userId).subscribe(userInfo => {
  console.log('Get User Info:', userInfo);
});
```

**7. getUsers** (!!CE VERSION!!)

```javascript
const userService = self.ctx.userService;
const userIds = ['your-user-i-1', 'your-user-i-2'];
userService.getUsers(userIds).subscribe(users => {
  console.log('List of Users:', users);
});
```

**8. getUserUsers**

```javascript
const userService = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getUserUsers(pageLink).subscribe(userUsers => {
  console.log('List of User Users:', userUsers);
});
```

**9. getAllUserInfos**

```javascript
const userService = self.ctx.userService;
const includeCustomers = true;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getAllUserInfos(includeCustomers, pageLink).subscribe(allUserInfos => {
  console.log('List of All User Infos:', allUserInfos);
});
```

**10. getCustomerUserInfos**

```javascript
const userService = self.ctx.userService;
const includeCustomers = true;
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.getCustomerUserInfos(includeCustomers, customerId, pageLink).subscribe(customerUserInfos => {
  console.log('List of Customer User Infos:', customerUserInfos);
});
```

**11. saveUser**

```javascript
const userService = self.ctx.userService;
const user = {  // User object
  // ... set the fields you need
};
const sendActivationMail = 'value';
const entityGroupIds = ['your-entity-group-i-1', 'your-entity-group-i-2'];
userService.saveUser(user, sendActivationMail, entityGroupIds).subscribe(savedUser => {
  console.log('Saved User:', savedUser);
});
```

**12. getActivationLink**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
userService.getActivationLink(userId).subscribe(activationLink => {
  console.log('Get Activation Link:', activationLink);
});
```

**13. getActivationLinkInfo**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
userService.getActivationLinkInfo(userId).subscribe(activationLinkInfo => {
  console.log('Get Activation Link Info:', activationLinkInfo);
});
```

**14. setUserCredentialsEnabled**

```javascript
const userService = self.ctx.userService;
const userId = 'your-user-id';
const userCredentialsEnabled = true;
userService.setUserCredentialsEnabled(userId, userCredentialsEnabled).subscribe(setUserCredentialsEnabled => {
  console.log('Set User Credentials Enabled:', setUserCredentialsEnabled);
});
```

**15. findUsersByQuery**

```javascript
const userService = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userService.findUsersByQuery(pageLink).subscribe(usersByQuerys => {
  console.log('List of Users By Querys:', usersByQuerys);
});
```
