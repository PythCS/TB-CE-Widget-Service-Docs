# USER

User management and authentication functions.

## Service Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

## Methods

### getUsers (!!CE VERSION!!)

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

userService.getUsers(pageLink).subscribe(users => {
  console.log('Users:', users);
});
```

### getTenantAdmins

```javascript
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

userService.getTenantAdmins(tenantId, pageLink).subscribe(admins => {
  console.log('Tenant Admins:', admins);
});
```

### getCustomerUsers

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

userService.getCustomerUsers(customerId, pageLink).subscribe(result => {
  console.log('CustomerUsers:', result);
});
```

### getUsersForAssign

```javascript
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

userService.getUsersForAssign(alarmId, pageLink).subscribe(users => {
  console.log('Users:', users);
});
```

### getUser

```javascript
const userId = 'your-user-id';

userService.getUser(userId).subscribe(result => {
  console.log('User:', result);
});
```

### getUsersByIds

```javascript
const userIds = 'your-users-id';

userService.getUsersByIds(userIds).subscribe(users => {
  console.log('Users:', users);
});
```

### saveUser

```javascript
const user = {
  // your user object
};
const sendActivationMail = {
  // your sendActivationMail object
};

userService.saveUser(user, sendActivationMail).subscribe(savedResult => {
  console.log('Saved Result:', savedResult);
});
```

### getActivationLink

```javascript
const userId = 'your-user-id';

userService.getActivationLink(userId).subscribe(url => {
  console.log('URL:', url);
});
```

### getActivationLinkInfo

```javascript
const userId = 'your-user-id';

userService.getActivationLinkInfo(userId).subscribe(info => {
  console.log('Info:', info);
});
```

### setUserCredentialsEnabled

```javascript
const userId = 'your-user-id';
const userCredentialsEnabled = true;

userService.setUserCredentialsEnabled(userId, userCredentialsEnabled).subscribe(result => {
  console.log('setUserCredentialsEnabled:', result);
});
```

### findUsersByQuery

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');

userService.findUsersByQuery(pageLink).subscribe(info => {
  console.log('Info:', info);
});
```

