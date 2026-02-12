# User Service

Complete reference for UserService - manage users, authentication, and user operations.

## Injection

```javascript
const $injector = self.ctx.$scope.$injector;
const userService = $injector.get(self.ctx.servicesMap.get('userService'));

// Alternative: Direct context access
const userService = self.ctx.userService;
```

## Methods

### getUsers (!!CE VERSION!!)

Get paginated list of users.

```javascript
const pageLink = self.ctx.pageLink(10, 0, '', 'email', 'ASC');
userService.getUsers(pageLink).subscribe(users => {
  console.log('List of Users:', users);
});
```

### saveUser

Create or update a user.

```javascript
const user = {
  email: 'newuser@example.com',
  firstName: 'John',
  lastName: 'Doe'
};
const sendActivationMail = true;
userService.saveUser(user, sendActivationMail).subscribe(savedUser => {
  console.log('Saved User:', savedUser);
});
```

### getUser

Get a specific user by ID.

```javascript
const userId = 'your-user-id';
userService.getUser(userId).subscribe(user => {
  console.log('User:', user);
});
```

## Common Use Cases

### User Management Dashboard

```javascript
// Get all tenant users
const pageLink = self.ctx.pageLink(50, 0, '', 'email', 'ASC');
userService.getUsers(pageLink).subscribe(users => {
  users.data.forEach(user => {
    console.log(`${user.email} - ${user.firstName} ${user.lastName}`);
  });
});
```

See the complete [UserService documentation](../DOCUMENTATION.md#user-service) for all 11 methods.