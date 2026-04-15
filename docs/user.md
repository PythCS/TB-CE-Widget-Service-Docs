# User

```javascript
// Service name: user
// File: user.service.ts
```

TO INJECT THE SERVICE:

```javascript
// Via direct context access (preferred)
const user = self.ctx.userService;
```

```javascript
// Via injector
const $injector = self.ctx.$scope.$injector;
const user = $injector.get(self.ctx.servicesMap.get('user'));
```

### **1. getUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
user.getUsers(pageLink).subscribe(users => {
  console.log('Users:', users);
});
```

### **2. getTenantAdmins**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
user.getTenantAdmins(pageLink).subscribe(tenants => {
  console.log('Tenants:', tenants);
});
```

### **3. getCustomerUsers**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
user.getCustomerUsers(pageLink).subscribe(customers => {
  console.log('Customers:', customers);
});
```

### **4. getUsersForAssign**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
user.getUsersForAssign(pageLink).subscribe(users => {
  console.log('Users:', users);
});
```

### **5. getUser**

```javascript
user.getUser(userId).subscribe(user => {
  console.log('User:', user);
});
```

### **6. getUsersByIds**

```javascript
user.getUsersByIds(userIds).subscribe(users => {
  console.log('Users:', users);
});
```

### **7. saveUser**

```javascript
user.saveUser(user, sendActivationMail).subscribe(user => {
  console.log('User:', user);
});
```

### **8. getActivationLink**

```javascript
user.getActivationLink(userId).subscribe(activationLink => {
  console.log('Activation Link:', activationLink);
});
```

### **9. getActivationLinkInfo**

```javascript
user.getActivationLinkInfo(userId).subscribe(activationLink => {
  console.log('Activation Link:', activationLink);
});
```

### **10. setUserCredentialsEnabled**

```javascript
user.setUserCredentialsEnabled(userId).subscribe(user => {
  console.log('User:', user);
});
```

### **11. findUsersByQuery**

```javascript
const pageLink = self.ctx.pageLink(10, 0, 'searchText', 'sortProperty', 'sortOrder');
user.findUsersByQuery(pageLink).subscribe(users => {
  console.log('Users:', users);
});
```
