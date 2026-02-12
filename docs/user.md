### **USER SERVICE**

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userservice = $injector.get(self.ctx.servicesMap.get('userservice'));

// Alternative: Direct context access
const userservice = self.ctx.userService;
```

**1. getUsers (!!CE VERSION!!)**

```javascript
const userservice = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userservice.getUsers(pageLink).subscribe(users => {
  console.log('Users:', users);
});
```

**2. getTenantAdmins**

```javascript
const userservice = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userservice.getTenantAdmins(pageLink, 'your-tenant-id').subscribe(tenantadmins => {
  console.log('Tenantadmins:', tenantadmins);
});
```

**3. getCustomerUsers**

```javascript
const userservice = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userservice.getCustomerUsers(pageLink, 'your-customer-id').subscribe(customerusers => {
  console.log('Customerusers:', customerusers);
});
```

**4. getUsersForAssign**

```javascript
const userservice = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userservice.getUsersForAssign(pageLink, 'your-alarm-id').subscribe(usersforassign => {
  console.log('Usersforassign:', usersforassign);
});
```

**5. getUser**

```javascript
const userservice = self.ctx.userService;
userservice.getUser('your-user-id').subscribe(user => {
  console.log('User:', user);
});
```

**6. getUsersByIds**

```javascript
const userservice = self.ctx.userService;
userservice.getUsersByIds('your-user-id').subscribe(usersbyids => {
  console.log('Usersbyids:', usersbyids);
});
```

**7. saveUser**

```javascript
const userservice = self.ctx.userService;
userservice.saveUser(user, true).subscribe(saveuser => {
  console.log('Saveuser:', saveuser);
});
```

**8. getActivationLink**

```javascript
const userservice = self.ctx.userService;
userservice.getActivationLink('your-user-id').subscribe(activationlink => {
  console.log('Activationlink:', activationlink);
});
```

**9. getActivationLinkInfo**

```javascript
const userservice = self.ctx.userService;
userservice.getActivationLinkInfo('your-user-id').subscribe(activationlinkinfo => {
  console.log('Activationlinkinfo:', activationlinkinfo);
});
```

**10. setUserCredentialsEnabled**

```javascript
const userservice = self.ctx.userService;
userservice.setUserCredentialsEnabled('your-user-id', true).subscribe(setusercredentialsenabled => {
  console.log('Setusercredentialsenabled:', setusercredentialsenabled);
});
```

**11. findUsersByQuery**

```javascript
const userservice = self.ctx.userService;
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
userservice.findUsersByQuery(pageLink).subscribe(usersbyquery => {
  console.log('Usersbyquery:', usersbyquery);
});
```

