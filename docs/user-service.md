# User Service (!!CE VERSION!!)

Manage users, permissions, and user-related operations in ThingsBoard. Note: Some methods behave differently between CE and PE versions.

## Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

## Methods

**1. getUsers** (!!CE VERSION!!)

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'email', 'ASC');

userService.getUsers(pageLink).subscribe(response => {
  console.log('Users:', response.data);
});
```
*Note: This method behaves differently between CE and PE versions. In CE, it may return an empty result for non-system administrators due to security restrictions.*

**2. getTenantAdmins**

```javascript
const tenantId = 'your-tenant-id';
const pageLink = self.ctx.pageLink(10, 0);

userService.getTenantAdmins(tenantId, pageLink).subscribe(response => {
  console.log('Tenant Admins:', response.data);
});
```

**3. getCustomerUsers**

```javascript
const customerId = 'your-customer-id';
const pageLink = self.ctx.pageLink(10, 0);

userService.getCustomerUsers(customerId, pageLink).subscribe(response => {
  console.log('Customer Users:', response.data);
});
```

**4. getUsersForAssign**

```javascript
const alarmId = 'your-alarm-id';
const pageLink = self.ctx.pageLink(10, 0);

userService.getUsersForAssign(alarmId, pageLink).subscribe(response => {
  console.log('Users for Alarm Assignment:', response.data);
});
```

**5. getUser**

```javascript
const userId = 'your-user-id';

userService.getUser(userId).subscribe(user => {
  console.log('User:', user);
});
```

**6. getUsersByIds**

```javascript
const userIds = ['user-id-1', 'user-id-2'];

userService.getUsersByIds(userIds).subscribe(users => {
  console.log('Users by IDs:', users);
});
```

**7. saveUser**

```javascript
const user = {
  email: 'john.doe@example.com',
  firstName: 'John',
  lastName: 'Doe',
  authority: 'CUSTOMER_USER',
  customerId: { entityType: 'CUSTOMER', id: 'your-customer-id' }
};
const sendActivationMail = true;

userService.saveUser(user, sendActivationMail).subscribe(savedUser => {
  console.log('Saved User:', savedUser);
});
```

**8. getActivationLink**

```javascript
const userId = 'your-user-id';

userService.getActivationLink(userId).subscribe(activationLink => {
  console.log('Activation Link:', activationLink);
});
```

**9. getActivationLinkInfo**

```javascript
const userId = 'your-user-id';

userService.getActivationLinkInfo(userId).subscribe(activationInfo => {
  console.log('Activation Link Info:', activationInfo);
});
```

**10. setUserCredentialsEnabled**

```javascript
const userId = 'your-user-id';
const userCredentialsEnabled = true; // Optional

userService.setUserCredentialsEnabled(userId, userCredentialsEnabled).subscribe(result => {
  console.log('User credentials status updated');
});
```

**11. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'john', 'email', 'ASC');

userService.findUsersByQuery(pageLink).subscribe(response => {
  console.log('Users by Query:', response.data);
});
```