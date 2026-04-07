# UserService

### **USERSERVICE

TO INJECT THE SERVICE:

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

**1. getUsers**

```javascript
userService.getUsers(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(uer => {
  console.log('Users:', uer);
});
```

**2. getTenantAdmins**

```javascript
userService.getTenantAdmins('your-tenant-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(tenantadmin => {
  console.log('Tenant Admins:', tenantadmin);
});
```

**3. getCustomerUsers**

```javascript
userService.getCustomerUsers('your-customer-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(cutomeruer => {
  console.log('Customer Users:', cutomeruer);
});
```

**4. getUsersForAssign**

```javascript
userService.getUsersForAssign('your-alarm-id', self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(usersforassign => {
  console.log('Users For Assign:', usersforassign);
});
```

**5. getUser**

```javascript
userService.getUser('your-user-id', { /* your config */ }).subscribe(user => {
  console.log('User:', user);
});
```

**6. getUsersByIds**

```javascript
userService.getUsersByIds(['id1', 'id2'], { /* your config */ }).subscribe(uerbyid => {
  console.log('Users By Ids:', uerbyid);
});
```

**7. saveUser**

```javascript
userService.saveUser({ /* your user object */ }, { /* your sendActivationMail */ }, { /* your config */ }).subscribe(savedUser => {
  console.log('Saved User:', savedUser);
});
```

**8. getActivationLink**

```javascript
userService.getActivationLink('your-user-id', { /* your config */ }).subscribe(activationlink => {
  console.log('Activation Link:', activationlink);
});
```

**9. getActivationLinkInfo**

```javascript
userService.getActivationLinkInfo('your-user-id', { /* your config */ }).subscribe(activationlinkinfo => {
  console.log('Activation Link Info:', activationlinkinfo);
});
```

**10. setUserCredentialsEnabled**

```javascript
userService.setUserCredentialsEnabled('your-user-id', true, { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```

**11. findUsersByQuery**

```javascript
userService.findUsersByQuery(self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder'), { /* your config */ }).subscribe(result => {
  console.log('Result:', result);
});
```
